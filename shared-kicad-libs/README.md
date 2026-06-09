# shared-kicad-libs

チーム共通のKiCadライブラリを管理するリポジトリ。基板は最新バージョンのみを置き、フットプリントもまとめて登録できるようにする。

構成例:

- `footprints/` : `.pretty` フォルダや `.kicad_mod` を配置
   - 基板設計で使うフットプリントをここに集約する
- `symbols/`    : シンボルファイル（`.kicad_sym`）を配置
- `3dmodels/`   : .step 等の3Dモデルを配置
- `fp-lib-table` と `sym-lib-table` : KiCad のライブラリテーブルのサンプル
- `drc_rules.kicad_dru` : チームで共有するDRCルールの例（参考）

初回セットアップ（メンバー側）:

1. リポジトリをローカルにクローン。
2. KiCad を開き、`設定` > `パスを設定`（Preferences > Configure Paths）で変数を追加:
   - 変数名例: `TEAM_SHARED_LIBS`
   - 値例（Windows）: `C:\\Users\\you\\git\\shared-kicad-libs`
3. KiCad のライブラリ管理で `fp-lib-table` / `sym-lib-table` をグローバルまたはプロジェクトに登録する。

運用ルール（推奨）:

- `Official_Parts` と `Sandbox` を分離し、設計時は `Official_Parts` のみ使用する。
- ライブラリ変更はブランチ→PR→レビュー→マージで行う。
- PR のチェックリストに「ドリル径・ランド径・3D割当・データシート照合」を含める。

このリポジトリのファイル例をコピーして運用に合わせて編集してください。
