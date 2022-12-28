# PHP Deploy

Deploy PHP Application to Server via SSH by RSync

## Config example:

```
name: Build and Deploy
on:
    push:
        branches:
            -   master

jobs:
    build:
        name: Build and Deploy
        runs-on: ubuntu-latest
        steps:
            -   name: Checkout Repository
                uses: actions/checkout@master

            -   name: Setup Enviroment
                uses: shivammathur/setup-php@v2
                with:
                    php-version: '7.1'

            -   name: Deploy to Server
                uses: lmribeiro/php-deploy@master
                with:
                    user: ${{ secrets.USER }}
                    host: ${{ secrets.HOST }}
                    path: ${{ secrets.PATH }}
                    owner: ${{ secrets.OWNER }}
                env:
                    DEPLOY_KEY: ${{ secrets.DEPLOY_KEY }}
```
