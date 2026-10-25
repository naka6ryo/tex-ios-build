# tex-ios-build

GitHub Actions のクラウドの Mac で、TeX Live 2026 の **e-upTeX**（pLaTeX 互換モードで動く）と **dvipdfmx** を、iPhone / iPad（arm64）向けの `.xcframework` にビルドするだけのリポジトリです。

自作の iPad 用 LaTeX エディタに組み込み、PC の TeX Live 2026 と同じ組版結果をオフラインで出すために使います。

## 中身

| ファイル | 役割 |
|---|---|
| `.github/workflows/build.yml` | ビルドの手順。Actions の画面から手動で実行する |
| `basic_Info.plist` | framework に入れる Info.plist のひな形（上流のスクリプトが参照するが、上流のリポジトリには無いため） |

## ビルドの元

- ソース: [holzschu/texlive-source](https://github.com/holzschu/texlive-source)（a-Shell の作者による、TeX Live 公式ソースに iOS 向けの変更を足したもの）のコミット `bfd21c360970869879d5ad89a2df8032962337ca` に固定
- 手順: 上流の `build_command.sh` をそのまま使い、作者の Intel Mac 前提の2か所（`--build` と `MAKE` のパス）だけを書き換える
- リンク先: [holzschu/ios_system](https://github.com/holzschu/ios_system) `v3.0.6`

## ライセンス

- このリポジトリのワークフローと設定ファイルは自由に使ってよい（CC0）
- ビルドされるプログラムは TeX Live の各ライセンス（多くは GPL）に従う。対応するソースは上のコミットにある
- ios_system は 3条項 BSD ライセンス
