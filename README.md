# Como Hospedar seus Levantamentos de Drone no GitHub Pages Grátis

Este repositório permite que você publique seus ortomosaicos e modelos 3D com um link permanente e gratuito no GitHub Pages (ex: `https://seu-usuario.github.io/meus-drones/`).

---

## 📁 Estrutura de Pastas

```text
meus-drones/
├── index.html            <- Página inicial que lista todos os seus clientes/voos
├── voo-fazenda-ouro/     <- Pasta de um voo específico
│   ├── index.html        <- Visualizador 2D/3D interativo
│   ├── tiles/            <- (Opcional) Fatias da ortofoto em pirâmide de zoom ({z}/{x}/{y}.png)
│   ├── orthophoto.jpg    <- Imagem da ortofoto (ou .png)
│   └── model.obj         <- Modelo 3D (ou .gltf)
└── demo-voo/             <- Exemplo pronto
    └── index.html
```

---

## 🚀 Passo a Passo para Publicar

### 1. Crie um repositório no seu GitHub
1. Vá em [github.com/new](https://github.com/new).
2. Dê um nome, por exemplo: `meus-drones` ou `levantamentos-aereos`.
3. Escolha **Público** (Public) e clique em **Create repository**.

### 2. Envie estes arquivos
No seu computador, abra a pasta `C:\Users\llsan\.gemini\antigravity\scratch\geodeploy-github-pages` e rode no terminal:
```bash
git init
git add .
git commit -m "Meu portal de drones"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/meus-drones.git
git push -u origin main
```
*(Ou se preferir, arraste e solte os arquivos diretamente pelo site do GitHub).*

### 3. Ative o GitHub Pages
1. No seu repositório no GitHub, clique na aba **Settings** (Configurações).
2. No menu lateral esquerdo, clique em **Pages**.
3. Em **Build and deployment** > **Branch**:
   - Selecione a branch `main` e a pasta `/ (root)`.
4. Clique em **Save**.

🎉 **Pronto!** Em cerca de 1 a 2 minutos, o GitHub vai gerar o link público:
👉 `https://SEU_USUARIO.github.io/meus-drones/`  
E para abrir o voo direto para o cliente:  
👉 `https://SEU_USUARIO.github.io/meus-drones/demo-voo/`

---

## 💡 Dica para Ortofotos Gigantes (>100MB)
O GitHub não aceita arquivos únicos maiores que 100MB. Para ortofotos de alta resolução:
1. No **WebODM** ou **QGIS**, exporte a ortofoto como **TMS / Leaflet Tiles** (gera uma pastinha cheia de imagens pequenas em `tiles/{z}/{x}/{y}.png`).
2. Cole essa pasta `tiles` dentro da pasta do voo. O mapa carregará instantaneamente com zoom fluido sem pesar no navegador do cliente!
