# ftp-action-studies

Automatize o envio de arquivos de FTP do seu site para o seu site lw!

## Exemplo de uso

```
name: Deploy via ftp
on: push
jobs:
  deploy:
    name: Deploy
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2

    - name: studies-lwftp-testing
      uses: allanalves23/ftp-action-studies@0.0.4
      with:
        host: ${{ secrets.HOST }} 
        user: ${{ secrets.USER }}
        password: ${{ secrets.PASS }}
        localDir: "dist"
```

## Parâmetros de uso

Input parameter | Description | Required | Default
--- | --- | --- | ---
host | Servidor FTP | Yes | N/A
user | Usuário FTP | Yes | N/A
password | Senha do usuário FTP | Yes | N/A
localDir | Diretório do projeto a ser copiado a sua hospedagem | No | .
remoteDir | Diretório da sua hospedagem que irá receber os arquivos copiados | No | "public_html"
forceSsl | Forçar encryptação SSL | No | false
options | Options adicionais | No | ''
