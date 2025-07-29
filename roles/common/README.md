# Common Role

全サーバー共通のシステムセットアップと設定タスクを管理するロールです。

## 機能

- 共通システムパッケージのインストール
- `/etc/hosts`ファイルの設定
- システムパッケージの更新（オプション）

## 変数

### defaults/main.yml
- `common_packages`: インストールするパッケージのリスト（デフォルト: curl, wget, git, htop, vim, unzip, tree）
- `hosts_backup`: hostsファイル変更前にバックアップを取るか（デフォルト: true）

### オプション変数
- `common_update_packages`: trueに設定するとシステムパッケージを更新（デフォルト: false）

## タグ

- `common`: このロールの全タスク
- `hosts`: hostsファイル設定のみ
- `update`: システムパッケージ更新のみ

## 使用例

```yaml
- hosts: all
  roles:
    - common
  vars:
    common_update_packages: true
```

## 依存関係

なし