# lftp-upload

Doc refer https://github.com/marketplace/actions/lftp-upload

Usage: same as above with --delete flag added.

```yaml
name: Deploy to FTP
on: push
jobs:
  ftp-deploy:
    runs-on: ubuntu-latest
    steps:
        - uses: actions/checkout@v2
        - name: Upload files to FTP
        uses: myyogateacher/lftp-wdupload@v2
        with:
            host: ${{ secrets.FTP_HOST }}
            username: ${{ secrets.FTP_USERNAME }}
            password: ${{ secrets.FTP_PASSWORD }}
            forceSsl: "true"
            localDir: ${{ secrets.FTP_LOCAL_DIR }}
            remoteDir: ${{ secrets.FTP_REMOTE_DIR }}
            timeout: "120"
            retries: "5"
            multiplier: "2.0"
            baseInterval: "10"
            pConn: "10"
```

