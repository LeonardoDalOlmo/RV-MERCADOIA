# RV-MERCADOIA

Build iOS do **Mercado AR** (Unity + AR Foundation/ARKit): um app que guia o cliente pelo mercado até os itens da
lista de compras, com uma seta na tela e a rota mais curta calculada sobre um grafo dos corredores.

Este repositório existe para compilar o app para iPhone **sem um Mac**:

1. `xcode/` guarda o projeto Xcode que a Unity gera no Windows (zip dividido em partes de 90 MB).
2. O workflow `.github/workflows/build-ipa.yml` roda num Mac do GitHub a cada push que muda `xcode/`,
   compila sem assinatura e publica o `MercadoAR.ipa` em **Actions ▸ execução ▸ Artifacts**.
3. No Windows, o [Sideloadly](https://sideloadly.io/) assina o `.ipa` com um Apple ID gratuito e instala no iPhone
   pelo cabo. Com conta gratuita, o app vale 7 dias.

## Atualizar o build

Depois de gerar um novo build iOS na Unity (`File ▸ Build Profiles ▸ iOS ▸ Build`), compacte a pasta gerada,
divida o zip em partes de até 90 MB com o nome `MercadoAR-iOS.zip.partNN`, atualize `MercadoAR-iOS.zip.sha256`
e faça push.
