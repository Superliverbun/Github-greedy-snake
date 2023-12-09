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
    name: generate animation

    on:
      schedule:
        - cron: "0 */6 * * *" # every 6 hours
      workflow_dispatch:
    
    jobs:
      generate:
        runs-on: ubuntu-latest
        timeout-minutes: 10
    
        steps:
          # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
          - name: generate github-contribution-grid-snake.svg
            uses: Platane/snk@master
            with:
              github_user_name: Superliverbun
              svg_out_path: dist/github-contribution-grid-snake.svg
    
          # push the content of <build_dir> to a branch
          # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
          - name: push github-contribution-grid-snake.svg to the output branch
            uses: crazy-max/ghaction-github-pages@v2.5.0
            with:
              target_branch: output
              build_dir: dist
            env:
              GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

**記得要存檔喔**


### Step 4. Run他

**1. 找到剛剛創的Action**</br>
![image](https://github.com/Superliverbun/Github-greedy-snake/assets/113052517/2b47826a-629a-499d-92cd-51534e7aab98)</br>
⭐他會叫generate animation</br>

**2. **
