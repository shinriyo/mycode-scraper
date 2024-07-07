# mycode download tool

## 説明

MYCODEがサービス終わったのでスクレイピングする。

https://github.com/tumf/mycode-scraper
こちらに元ネタです。
ローカル環境を汚したくないのでDockerで動く様にしました。
Driver部分も変更しています。
あとM1 Maxで動作するようにしたのでそれ以外のCPUで動くかはわかりません。

### 内容

```
mycode-scraper
├── docker-compose.yml
├── py_context
│   ├── Dockerfile
│   └── requirements.txt
└── work
    ├── localize_web_assets.py
    └── scrape.py
```

### 使い方

```
cd PythonSelenium
docker-compose build
docker-compose up -d                 # detouched mode option
docker-compose exec python bash      # 起動したPythonコンテナに入る 
```

`saved_pages` フォルダに入ると思います。

### 実行

```bash
MYCODE_EMAIL=you@example.com MYCODE_PASSWORD=p@ssw0rd python scrape.py
```
※Eメールアドレスと、パスワードを読み替えること

実行時にCAPTCHAとかパスワードのヒントを求められるので以下URLでブラウザに入って入力してからEnterすること。

http://localhost:7900/?autoconnect=1&resize=scale&password=secret

### Pyyhonコンテナに入ってる時に動かない時

```
exit
docker-compose restart
```


