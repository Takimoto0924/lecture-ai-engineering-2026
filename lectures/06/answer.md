# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前：glossary_search_glossary

- STEP 2 の [tool call]：`glossary_search_glossary({'query': '3レベル'})`

- STEP 3 の [tool call]：`fetch_fetch({'url': 'https://modelcontextprotocol.io/'})`

- STEP 4 の [tool call]：
    - `aws_aws___search_documentation({'search_phrase': 'Amazon S3 バージョニング 概要', 'topics': ['general']})`
    - `aws_aws___search_documentation({'search_phrase': 'Using versioning in S3 buckets', 'topics': ['general']})`

- 気づき・疑問：
    - STEP 3 では、`fetch_fetch` の実行に失敗することが多かった。また、取得に成功した場合でも、追加で別の Web ページを参照することがあった。
    - 別の失敗例では、`fetch_fetch` の実行後に `glossary_search_glossary` が呼び出されていた。これは、MCP という用語に反応して、用語集を検索する必要があるとモデルが判断したためだと考えられる。

## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：発展

- やったこと：
    - Codex の公式ドキュメントで MCP サーバーの設定方法を調べ、演習で使用した `app/mcp_servers.json` と比較した。
- 結果：
    - 設定ファイル：演習では JSON 形式を使用するが、Codex では TOML 形式の `config.toml` を使用する。
    - コマンドによる起動：演習と同様に `command` と `args` を指定する。
    - URL による接続：演習と同様に `url` を指定する。
    - 有効範囲：`~/.codex/config.toml` ではユーザー単位、`.codex/config.toml` では信頼済みのプロジェクト単位で設定できる。
- 気づき・疑問：
    - 設定ファイルの形式は異なるものの、MCP サーバーの基本的な設定項目は共通していることが分かった。
    - 設定ファイルの形式も統一されれば、異なるソフトウェア間で設定を共有しやすくなるのではないかと感じた。