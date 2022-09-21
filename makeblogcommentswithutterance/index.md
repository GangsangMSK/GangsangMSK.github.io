# [Blog] utterance를 이용한 블로그 댓글 기능 만들기


## utterance를 사용한 이유

댓글 기능을 구현할 수 있는 여러 종류(disqus, gittalk, giscus 등)의 댓글 플랫폼들이 있지만, 많은 플랫폼 중에 utterances를 선택한 이유는 다음과 같다.

* utterances는 Github 계정 로그인을 통해 댓글을 달고, 댓글이 달리면 알림이 Github Repository 의 Issue 로 올라오는 시스템이여서 댓글이 달리면 메일로 댓글 알림을 받을 수 있다.

* 그리고 광고가 없고 가볍다.

* 마지막으로, 마크다운 문법을 사용할 수 있다.

## utterances 적용하기

### 1. Issue(댓글)이 저장될 Repository를 정하거나 생성한다.

* 나는 기존 블로그용으로 사용하는 GangsangMSK.github.io Repository를 정했다.

### 2. utterance를 설치하기

https://github.com/apps/utterances 링크를 통해 설치할 수 있다.   

![1](/images/Blog/MakeBlogCommentsWithUtterance/1.png)   

설치를 할 때, 전체 Repository의 Issue 들에 업로드가 되게 할지, 아니면 특정한 저장소의 Issue 에만 업로드가 되게 할지 선택할 수 있다. 사진과 같이 Only select reposioires를 통해, Issue(댓글)가 올라올 Repository를 위에서 선택한 후 Install 하면 된다.

### 3. Install 후 페이지 작성

https://utteranc.es 에 접속하여 다음과 같은 페이지를 작성한다.

![2](/images/Blog/MakeBlogCommentsWithUtterance/2.png)


repo
* 위에서 Issue가 올라올 곳으로 선택한 Repositoty 를 써준다. (github아이디/저장소이름)
* ex) GangsangMSK/GangsangMSK.github.io
* ex) GangsagnMSK/blog-comments

Blog Post <-> Issue Mapping
* Issue가 달린 블로그 페이지의 어떤 부분과 매핑을 시킬지 Key 값을 결정한다.
* 매핑시키는 것이니만큼 Key 값이 달라지면 Value 갑은 사라질 것이다. 수정을 하지 않는 pathname을 선택한다.

### 4. 블로그에 적용하기

![3](/images/Blog/MakeBlogCommentsWithUtterance/3.png)

페이지 작성 시, 위와 같이 스크립트를 자동으로 생성해준다. 이를 복사하거나 참고하여 블로그에 적용시켜준다.

내가 쓰는 Hugo의 LoveIt 테마 같은 경우

![4](/images/Blog/MakeBlogCommentsWithUtterance/4.png)

위와 같이 적용시켜준다.

## 참고자료

[[Github 블로그] utterances 으로 댓글 기능 만들기 (+ disqus 비추후기)](https://ansohxxn.github.io/blog/utterances/)
