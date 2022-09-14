# hugo & Github을 사용한 블로그 구축

> ## 개발환경
* Hardware : Macbook Pro(16-inch,M1,2021)
* OS : macOS Monterey 12.5
* Shell : zsh
* hugo : hugo v0.102.3+extended darwin/arm64
* brew : Homebrew 3.6.1

> ## 블로그 구축 방법
1. Github repository 생성

    블로그 구축을 위해   
    * 소스 원본 저장 및 관리용    
    개발용(Development) repository : blog

    * 개발용 repository를 빌드한 결과물   
    서비스용 repositoty : (username).github.io

    2개의 repository를 생성한다.    

    2개의 repository 사용은 블로그를 운영하는 데에 필수는 아니지만, 일괄적으로 Github repository에서 글 작성, 변경이나 버전 관리 등이 편하기에 사용한다.

2. Hugo 설치

    Homebrew를 사용하여 hugo 설치   

    ```
    $ brew install hugo
    ```

    ***

    hugo가 설치되었는지 확인   

    ```
    $ brew version   
    hugo v0.102.3+extended darwin/arm64 BuildDate=unknown
    ```   

    정상적으로 hugo가 설치되었으면 버전이 출력된다.    

3. 사이트 생성

    프로젝트를 만들 폴더로 이동한다.

    ```
    $ pwd
    /Users/ms

    ## 트리 구조로 본 프로젝트 경로
    /
    └── Users
        └── ms
            └── blog <== 내가 새로 만들 블로그 폴더


    ```   

    ***

    사이트 생성 명령어 
    ``` 
    $ hugo new site [프로젝트 이름(폴더 명)]
    ``` 

    ``` 
    $ hugo new site blog
    Congratulations! Your new Hugo site is created in /Users/ms/blog.

    Just a few more steps and you're ready to go:

    1. Download a theme into the same-named folder.
    Choose a theme from https://themes.gohugo.io/ or
    create your own with the "hugo new theme <THEMENAME>" command.
    2. Perhaps you want to add some content. You can add single files
    with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
    3. Start the built-in live server via "hugo server".

    Visit https://gohugo.io/ for quickstart guide and full documentation.
    ``` 

    메세지와 함께 blog 폴더가 생성된 걸 확인할 수 있다.

4. 테마 다운로드

    현재 블로그 테마는 [LoveIt](https://themes.gohugo.io/themes/loveit/#why-choose-loveit)을 사용하고 있다.

    블로그 프로젝트 폴더로 이동하여 **git init** 명령어를 통해 git 환경을 구성한다.

    ``` 
    $ pwd
    /Users/ms/blog
    $ git init
    ``` 

    ***

    #### 서브모듈(submodule)의 개념

    Git의 서브모듈(Submodule)이란 하나의 저장소(Repository) 안에 있는 또 다른 별개의 저장소이다.   
    보통 다른 원격 저장소를 가져와(Pull) 서브모듈로 사용하게 된다.

    ***

    #### 테마 깃허브 저장소를 서브모듈로 가져오기

    ``` 
    $ pwd
    /Users/ms/blog
    $ git submodule add https://github.com/dillonzq/LoveIt.git themes/LoveIt
    ``` 

    ***

    **git submodule** 명령어를 통해 submodule 목록이 생성된 걸 확인할 수 있다.

    ``` 
    $ git submodule
    e9e89a4613baee823596822b7d246f5931263491 themes/LoveIt (v0.2.11-143-ge9e89a4)
    ``` 

    ***

    #### 설정파일(config.toml) 생성

    다음으로 themes/LoveIt/exampleSite/config.toml 파일을 복사해 초기에 생성된 config.toml 에 덮어쓴다.

    ```
    .
    ├── archetypes
    ├── config.toml <== 초기에 생성된 config.toml
    [...]
    └── themes
        └── LoveIt
            └── exampleSite
                └── config.toml <== 복사할 config.toml
    ```

    교체된 config.toml 설정파일을 열어보면 themesDir 값을 삭제하고 저장한다.

    ***

    #### 게시글 생성

    LoveIt 테마에서는 **/content/posts/** 폴더 아래에 게시글이 생성되어야 정상적으로 출력된다.

    테마마다 게시글이 위치해야하는 경로나 이름이 다를 수 있다. 테마 페이지에서 안내해주는 가이드 문서를 참고하여 게시글을 해당 경로에 맞게 생성해야 한다.

    ***

    #### Front Matter 설명
    
    * title : 게시글의 제목

    * date : 게시글의 최초 작성시간

    * lastmod : 게시글의 마지막 수정시간

    * description : 게시글의 설명. 검색엔진 최적화(SEO, Search Engine Optimization)를 위해서 게시글 제목(title)에 담긴 내용을 풀어 간단하게 적어놓는다.

    * draft :  draft: true 일 경우, 실제 배포환경에서 해당 게시글은 보이지 않게 된다. 작성한 글을 개발 환경이 아닌 실제 환경에도 게시하고 싶다면 반드시 draft: false 값을 설정한다.

    * tags : 게시글의 태그

    * toc : table of content의 약자. Front Matter의 값이 toc: true 일 경우 마크다운 기반의 게시글 목차를 정리해서 보여준다.
    
    * categories : 게시글의 목록

    ***

    ```
    $ hugo new posts/FirstPost.md <== 포스트 만들기
    $ hugo serve <== 로컬호스트 서버 실행하기
    ```

    ```
    Start building sites …
    hugo v0.102.3+extended darwin/arm64 BuildDate=unknown
    WARN 2022/09/14 16:27:51

    Current environment is "development". The "comment system", "CDN" and "fingerprint" will be disabled.
    当前运行环境是 "development". "评论系统", "CDN" 和 "fingerprint" 不会启用.

                    | EN
    -------------------+-----
    Pages            | 19
    Paginator pages  |  0
    Non-page files   |  0
    Static files     | 75
    Processed images |  0
    Aliases          |  6
    Sitemaps         |  1
    Cleaned          |  0

    Built in 55 ms
    Watching for changes in /Users/ms/blog/{archetypes,content,data,layouts,static,themes}
    Watching for config changes in /Users/ms/blog/config.toml, /Users/ms/blog/themes/LoveIt/config.toml
    Environment: "development"
    Serving pages from memory
    Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
    Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
    Press Ctrl+C to stop
    ```

    마지막에 Web Server is available at http://localhost:1313/ 메세지가 출력되면 정상적으로 완료된 것이다.

    인터넷 브라우저를 열어 http://localhost:1313/ 으로 접속한다. 블로그가 제대로 실행되는지 확인한다

5. git remote 추가

    **명령어 형식**
    ```
    $ git remote add origin [개발용 repository의 URL]
    ```
    * git remote : 현재 프로젝트에 등록된 리모트 저장소를 확인하는 명령어이고 리모트 저장소의 단축 이름을 보여준다. 레포지터리를 복제(Clone)하면 origin이라는 리모트 저장소가 자동으로 등록되기 때문에 origin이라는 이름을 볼 수 있다.

    * origin : 축약형 이름을 말한다.

    * 개발용(Development) repository의 URL : https://github.com/<Github 유저네임>/<블로그용 레포지터리 이름>

    ***

    리모트 저장소가 정상적으로 추가되었는지 git remote -v 명령어로 확인한다.

    -v 옵션을 주면 등록된 리모트 저장소의 이름과 URL을 같이 볼 수 있다.

    ```
    $ git remote -v
    origin	https://github.com/GangsangMSK/blog.git (fetch)
    origin	https://github.com/GangsangMSK/blog.git (push)
    ```

6. 서브모듈 추가

    ```
    $git submodule add -b master https://github.com/GangsangMSK/GangsangMSK.github.io.git public
    ```

    서브모듈를 추가한 후에 정삭적으로 작동하는지 git submodule 명령어로 확인한다.

    ```
    $ git submodule
    611a839e05691470e202ce54c4b7abc1b7f0269b public (heads/master)
    e9e89a4613baee823596822b7d246f5931263491 themes/LoveIt (v0.2.11-143-ge9e89a4)
    ```

    public 폴더가 submodule로 추가된 걸 확인할 수 있다.

7. 배포

    이제 hugo 블로그를 관리하려면 개발용과 서비스용 repository에 모두 commit을 해야한다. 이렇게 구분된 repository 경로마다 들어가서 commit과 push를 총 2번 해야하는 불편함이 있기에 컨텐츠를 자동으로 배포하는 스크립트를 작성한다.

    ```
    .
    ├── archetypes
    ├── content
    ├── data
    ├── layouts
    ├── public
    ├── resources
    ├── static
    ├── deploy.sh <== 우리가 작성할 스크립트 파일(생성 위치)
    └── themes
        └── hugo-theme-codex

    ```

    ```
    #!/bin/bash

    echo -e "\033[0;32mDeploying updates to GitHub...\033[0m"

    # Build the project.
    # hugo -t <여러분의 테마>
    hugo -t LoveIt

    # Go To Public folder, sub module commit
    cd public
    # Add changes to git.
    git add .

    # Commit changes.
    msg="rebuilding site `date`"
    if [ $# -eq 1 ]
    then msg="$1"
    fi
    git commit -m "$msg"

    # Push source and build repos.
    git push origin master

    # Come Back up to the Project Root
    cd ..

    # blog 저장소 Commit & Push
    git add .

    msg="rebuilding site `date`"
    if [ $# -eq 1 ]
    then msg="$1"
    fi
    git commit -m "$msg"

    git push origin master

    ```
    
    ***

    게시글을 작성한 후에, 블로그에 게시하기 위하여 배포용 쉘스크립트인 deploy.sh만 사용하면 된다.

    macOS 환경에서는 터미널에서 bash 명령어를 기본적으로 지원한다.

    ```
    $ bash deploy.sh
    ```

    ```
    $ bash deploy.sh
    bash deploy.sh
    Deploying updates to GitHub...
    Start building sites … 
    hugo v0.86.0+extended darwin/arm64 BuildDate=unknown

                    | EN  
    -------------------+-----
    Pages            | 14  
    Paginator pages  |  0  
    Non-page files   |  0  
    Static files     | 12  
    Processed images |  0  
    Aliases          |  0  
    Sitemaps         |  1  
    Cleaned          |  0  

    Total in 33 ms
    [...]
    remote: Resolving deltas: 100% (5/5), completed with 5 local objects.
    To https://github.com/GangsangMSK/blog
    fa10865..e13e834  master -> master
    ```


    정상적으로 게시글 배포가 완료된다.

> ## 참고자료

[Hugo-LoveIt 테마 구축 방법](https://hugoloveit.com/theme-documentation-basics/)

[Hugo x github 블로그 설치 방법](https://seyslee.github.io/blog/installing-hugo-github-blog/)

