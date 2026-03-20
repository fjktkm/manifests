# manifests

Raspberry Pi 3 台で構成した `k3s` クラスタを `Argo CD` で GitOps 運用するためのリポジトリ。

## 概要

2026-03-21 時点で、3 台構成の `k3s` 高可用性クラスタは稼働しており、`Argo CD` の基本コンポーネントも導入済み。

- このリポジトリの `origin` は `https://github.com/fjktkm/manifests.git`
- 最小 bootstrap 用マニフェストは `bootstrap/` 配下に配置済み

## 公開できる現在の状態

- クラスタは 3 台の control plane / etcd 構成
- `k3s v1.34.5+k3s1` が稼働中
- `Argo CD` は `argocd` namespace に導入済み
- `argocd-server`, `argocd-repo-server`, `argocd-application-controller` を含む主要 Pod は `Running`
- ローカル接続用の `kubeconfig` は生成済みだが Git 管理外

想定する構成:

- 3 台とも `k3s server` (`control plane` 兼 `worker`)

3 台構成のため、単一 `control plane` にせず、3 台すべてを `control plane` 兼 `worker` として使う方針とする。`k3s` では embedded etcd を使った高可用性構成を目指す。

## bootstrap

現時点では、Argo CD の root Application 用に最低限の manifest を配置している。

- `bootstrap/project.yaml`
- `bootstrap/root-application.yaml`
- `bootstrap/apps/platform-namespaces.yaml`

最初の子 `Application` として、`platform/namespaces` を管理対象にしている。

`origin/main` に反映後、root Application を apply して GitOps 管理へ移行する。

## ローカル運用情報

公開したくない運用情報は `README.md` には書かず、Git 管理外の `.codex/` 配下で管理する。

- 例: ノードの接続先、内部 IP、ローカルの接続手順、再取得コマンド
- `.codex/` と `kubeconfig/` は `.gitignore` に入れている

## 次にやること

1. このリポジトリの変更をコミットして `origin/main` に push する
2. `bootstrap/project.yaml` と `bootstrap/root-application.yaml` をクラスタへ apply する
3. 実運用する `Application` 群とディレクトリ構成を決める
4. `Argo CD` の公開方法と認証運用を決める

## メモ

- `Argo CD` インストール時、通常の client-side apply では CRD annotation サイズ制限に当たったため、server-side apply で導入した
- `Application` 単体で始めるか、App of Apps 構成にするかは今後決める
- `worker` 専用ノードは設けず、3 台とも workload を載せる前提で進める
