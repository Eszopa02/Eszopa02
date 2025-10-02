## ABOUT ME:
My name is Eden. I'm a recent graduate from Columbia College Chicago, with a Bachelor's degree in Game Design & Development, as well as a Master's degree in User Experience and Interaction Design. 
Currently working as a Senior Project Advisor at REACH Pathways on their educational app.
During my free time, I enjoy designing and playing games, writing, and scrapbooking. 

***
### SOCIALS:
***
[![Portfolio Banner](https://img.shields.io/badge/Portfolio-255E63?style=for-the-badge&logo=About.me&logoColor=white)](https://sites.google.com/view/szopa-portfolio/projects) [![LinkedIn Banner](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/eszopa/) [![YouTube Banner](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@TodaysAnAdventure)  [![Itch.io Banner](https://img.shields.io/badge/Itch.io-FA5C5C?style=for-the-badge&logo=itchdotio&logoColor=white)](https://on-an-adventure.itch.io/) [![Patreon Banner](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://patreon.com/OnAnAdventure?utm_medium=unknown&utm_source=join_link&utm_campaign=creatorshare_creator&utm_content=copyLink) 

***
### TECH STACK:
***
**Programming Language**

![C# Banner](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white)

**Game Engines**

![Unity Banner](https://img.shields.io/badge/Unity-100000?style=for-the-badge&logo=unity&logoColor=white) ![Unreal Engine Banner](https://img.shields.io/badge/-Unreal%20Engine-313131?style=for-the-badge&logo=unreal-engine&logoColor=white)


**Developer Tools**

![GitHub Banner](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white) ![Visual Studio Banner](https://img.shields.io/badge/Visual_Studio-5C2D91?style=for-the-badge&logo=visual%20studio&logoColor=white) ![Canva Banner](https://img.shields.io/badge/Canva-%2300C4CC.svg?&style=for-the-badge&logo=Canva&logoColor=white) ![Figma Banner](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white) ![Miro Banner](https://img.shields.io/badge/Miro-F7C922?style=for-the-badge&logo=Miro&logoColor=050036)

**Project Management Software**

![JIRA Banner](https://img.shields.io/badge/Jira-0052CC?style=for-the-badge&logo=Jira&logoColor=white) ![Asana](https://img.shields.io/badge/Asana-009DFF?style=for-the-badge&logo=asana&logoColor=white) ![Airtable Banner](https://img.shields.io/badge/Airtable-18BFFF?style=for-the-badge&logo=Airtable&logoColor=white) ![Trello Banner](https://img.shields.io/badge/Trello-0052CC?style=for-the-badge&logo=trello&logoColor=white) ![Notion Banner](https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=notion&logoColor=white)

***
### GITHUB STATS
****

[![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=Eszopa02&theme=nightowl&show_icons=true)](https://github.com/anuraghazra/github-readme-stats)



name: Generate Snake

on:
  schedule:
    # Run every 12 hours
    - cron: "0 */12 * * *"

  # Allow manual triggering of the workflow
  workflow_dispatch:

  # Run on pushes to the main branch
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      # Step 1: Clone the repository
      - name: Clone repo
        uses: actions/checkout@v3

      # Step 2: Generate the snake files
      - name: Generate the snake files in './dist/'
        uses: Platane/snk@v3
        id: snake-gif
        with:
          github_user_name: {GITHUB_USERNAME}  # Replace with your GitHub username
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
            dist/github-contribution-grid-snake.gif?color_snake=orange&color_dots=#bfd6f6,#8dbdff,#64a1f4,#4b91f1,#3c7dd9
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

      # Step 3: Show the status of generated files
      - name: Show build status
        run: git status

      # Step 4: Push the new files to the output branch
      - name: Push new files to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output  # Branch where the generated files will be pushed
          build_dir: dist
          commit_message: Update snake animations
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}


<!--
**Eszopa02/Eszopa02** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
