ディレクトリ構成：

ルート
├── docker
│   ├── mysql　mysql用のコンテナ設定
│   │   ├── Dockerfile
│   │   └── data　ここにmysqlのデータファイル類を格納する
│   └── php　PHP、apache用のコンテナ設定
│       ├── 000-default.conf
│       └── Dockerfile
├── docker-compose.yml
├── src　laravelのプロジェクトファイル一式を格納する場所
│   └── readme.txt
└── tree.txt

注意点：
「./docker/mysql/data/readme.txt」は、dockerビルド時は削除すること。
「./docker/mysql/data/readme.txt」を作成した理由は、dataフォルダを作るため

