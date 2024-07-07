# mycode download tool

## 説明

MYCODEが終わったのでスクレイピングする。

### 内容

mycode-scraper
├── docker-compose.yml
├── py_context
│   ├── Dockerfile
│   └── requirements.txt
└── work
    ├── localize_web_assets.py
    └── scrape.py

### 使い方

```
cd PythonSelenium
docker-compose build
docker-compose up -d                 # detouched mode option
docker-compose exec python bash      # 起動したPythonコンテナに入る 
```

### 実行

```bash
MYCODE_EMAIL=you@example.com MYCODE_PASSWORD=p@ssw0rd python scrape.py
```

パスワードを読み替えること

### Pyyhonコンテナに入ってる時に動かない時

```
exit
docker-compose restart
```

### URL

http://localhost:7900/?autoconnect=1&resize=scale&password=secret

