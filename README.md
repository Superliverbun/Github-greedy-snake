## Github 貢獻貪食蛇教學

#### 想要做出超酷的貪食蛇嗎
#### 照著以下的步驟來變出蛇蛇吧🐍
![](https://github.com/Superliverbun/Superliverbun/blob/output/github-contribution-grid-snake.svg)

-----
### Step 1. 創建一個與你的使用者ID相同的儲存庫(repository)
<img src="https://github.com/Superliverbun/Github-greedy-snake/assets/113052517/64bd9697-18d7-46a1-a608-a33f64c9f82a" width = "1000px"/></br>
⭐記得要加README file喔！！

### Step 2. 新增一個Action
**1. 點Action**</br>
![image](https://github.com/Superliverbun/Github-greedy-snake/assets/113052517/26220c5a-6c98-4f40-9f68-5a5b35877824)</br>
**2. 點New Workflow**</br>
![image](https://github.com/Superliverbun/Github-greedy-snake/assets/113052517/84d1e05b-31cd-409f-bb91-22fb58f74930)</br>
**3. 點Configure**</br>
![image](https://github.com/Superliverbun/Github-greedy-snake/assets/113052517/c974c59d-b36d-4a52-b096-0734cef0eb0b)</br>


### Step 3. 編輯檔名和內容

#### 1.檔名取你喜歡的就可以了
![image](https://github.com/Superliverbun/Github-greedy-snake/assets/113052517/bd4d2ce0-9c6d-4a52-8f80-080a4e938251)
#### 2.內容請全部刪掉，改成以下內容
       name: generate-snake
       
       on:
         # run automatically every 12 hours
         schedule:
           - cron: "0 */12 * * *"
       
         # allows to manually run the job at any time
         workflow_dispatch:
       
         # run on every push on the master branch
         push:
           branches:
           - master
       
       
       
       jobs:
         generate:
           runs-on: ubuntu-latest
           timeout-minutes: 10
       
           steps:
             # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
             - name: Generate github-contribution-grid-snake.svg
               uses: Platane/snk/svg-only@v3
               with:
                 github_user_name: ${{ github.repository_owner }}
                 outputs: |
                   dist/github-contribution-grid-snake.svg
                   dist/github-contribution-grid-snake-dark.svg?palette=github-dark
               env:
                 GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
                 
             # push the content of <build_dir> to a branch
             # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
             - name: Push github-contribution-grid-snake.svg to the output branch
               uses: crazy-max/ghaction-github-pages@v3.1.0
               with:
                 target_branch: output
                 build_dir: dist
               env:
                 GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
**記得要存檔喔**


### Step 4. Run他


![image](https://github.com/Superliverbun/Github-greedy-snake/assets/113052517/5562cfb9-36f0-4697-bca5-316190cd0740)</br>
⭐他會叫**generate-snake-v2**</br>

(帶編輯)
