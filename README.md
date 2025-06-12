<p align="center">
  <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExd25ucnFld250aGJveXNhYmZqN3N5Zzh4Y2h6dDI4aGFocWN2azI1ZyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/qgQUggACpCjo6iFRwO/giphy.gif" width="100%" alt="Banner animado"/>
</p>

<div align="center">
  <a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=30&pause=1000&color=39FF14&center=true&vCenter=true&width=435&lines=Ol%C3%A1%2C+eu+sou+o+bielszn!;Estudante+de+Ci%C3%AAncia+da+Computa%C3%A7%C3%A3o;Apaixonado+por+tecnologia;Sempre+buscando+me+aprimorar." alt="Typing SVG" /></a>
</div>

<p align="center">
  <a href="https://www.linkedin.com/in/SEU-LINKEDIN/" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:SEU-EMAIL@gmail.com" target="_blank"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"></a>
</p>

---

## 👾 Sobre Mim

<p align="center">
  Olá! Sou estudante de <b>Ciência da Computação</b> e um verdadeiro apaixonado por tecnologia. Estou sempre fuçando, aprendendo e buscando me aprimorar. Este GitHub é o meu cantinho para mostrar alguns dos projetos que venho desenvolvendo na minha jornada. Sinta-se à vontade para explorar!
</p>

---

## 🛠️ Ferramentas

<p align="center">
  <img src="https://skillicons.dev/icons?i=html,css,js" /><br>
</p>

---

## 📊 Estatísticas do GitHub

<p align="center">
  <img height="180" src="https://github-readme-stats.vercel.app/api?username=bielszn&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true&count_private=true&bg_color=0D1117" alt="Estatísticas do GitHub de bielszn"/>
  
  <img height="180" src="https://github-readme-stats.vercel.app/api/top-langs/?username=bielszn&layout=compact&langs_count=8&theme=tokyonight&hide_border=true&bg_color=0D1117" alt="Linguagens Mais Usadas por bielszn"/>
</p>

---

## 🐍 Minha Cobrinha de Contribuições

<p align="center">
  <img src="https://raw.githubusercontent.com/bielszn/bielszn/output/github-contribution-grid-snake.svg" alt="Animação da Cobrinha de Contribuições">
</p>

# GitHub Action para gerar a animação da cobrinha

name: Generate Snake Animation

on:
  schedule:
    - cron: "0 */6 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      # Gera o arquivo SVG da cobrinha
      - name: Generate Snake SVG
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: bielszn # Seu username aqui
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark

      # Publica o arquivo gerado em um branch chamado "output"
      - name: Push to GitHub
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
