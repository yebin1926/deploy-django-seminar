# 12기 GitHub 협업 가이드라인(운영진용)

## 목적

1. 원활한 세미나 준비 및 레포지토리 효율적 관리
2. 세미나 준비 과정 자체가 운영진들에게 도움이 되었으면 하는 바램
3. 운영진 스스로 협업 과정에 익숙해져야 12기들에게 GitHub 지도 및 이슈 해결이 원활함

## 방식

### 레포지토리 구성

`**AAA-seminar**` : 12기 ‘AAA’ 주제 세미나 진행에 사용될 레포지토리

- 관련 내용 : [12기 GitHub 협업 가이드라인(세미나 진행)](https://www.notion.so/12-GitHub-e3df666ed0f440bfa91fbc49c5cccc5c?pvs=21)

`**AAA-solution**` : ‘AAA’ 세미나 주제 준비 → 완성 코드 레포지토리

<aside>
⚠️ `**-solution**` 레포지토리는 개인 별로 접근 권한이 다르니 혹시 문제가 있는 경우 연락주세요!

</aside>

### 브랜치 구성

- 브랜치를 태스크 또는 피쳐 별로 나누면 더 보기 좋지만 사람도 많고 빠른 진행을 위해 우선 `**주차-본인이름**` 형식으로 통일하겠습니다.
- 같은 주제 내에서는 이전 주차의 내용을 그대로 이어 받아 진행하게 되는 세미나의 특성 상 최대한 순차적으로 코드 준비를 하는 것이 좋을 것 같다고 생각합니다.
- 주차 별 개인 작업 브랜치에서 작업한 내용을 완성본 브랜치로 병합하며, 해당 주차 검토 및 수정이 완료된 이후 **`main`**에 병합합니다.
- 브랜치 분기는 **`main`** → `**week#-solution**` → `**week#-name**` 순이며 구현이 완료됨에 따라 역순으로 병합합니다.
- `**week#-name**` 브랜치는 origin에 흔적이 남지 않도록 가급적이면 push하지 않고 **local에서만 작업**합니다.

**주차 별 개인 작업 브랜치**

**`week#-name`** : ex) **`week8-dongjae`** **`week8-jaewon`** **`week9-suhyuk`**

---

**주차 별 세미나 및 과제 완성본 브랜치**

**`week#-solution`** : ex) **`week8-solution`**

---

**레포지토리 별 솔루션 브랜치**

`**main**` : week#-solution 브랜치가 코드 구현에 따라 차례로 병합되어 최종적으로 전체 솔루션이 포함됩니다.

---

<aside>
⚠️ `**main` 레포지토리에 포함되지 않는 소스 코드의 공유가 필요한 경우 자유롭게 브랜치명을 결정**

ex) React 실습 세미나에서 Main Blog와 관련 없는 새로운 웹페이지의 경우 → **`week##-hook-practice`**

</aside>

**작업 플로우**

ex) 6~9주차 django 세미나 → week8 준비

1. 7주차 코드가 완성되기 전 **노션 자료 초안(자료 목차, 코드 스니펫 및 실습 스크린샷을 제외한 세미나 자료)**을 **우선 작성**
2. 8주차 발표자 회의를 통해 8주차에 개발할 태스크들을 알아서 분담합니다
3. 7주차 코드가 `week7-solution`에 완성되었다면 아래와 같이 `main` ←`week7-solution` **머지(Pull Request)**되어있을 것.
    
    ![Untitled](12%E1%84%80%E1%85%B5%20GitHub%20%E1%84%92%E1%85%A7%E1%86%B8%E1%84%8B%E1%85%A5%E1%86%B8%20%E1%84%80%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%86%AB(%E1%84%8B%E1%85%AE%E1%86%AB%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC)%20ba82a8ff99f34102917434d6156f37ac/Untitled.png)
    
4. `main` → `week8-solution` branch 생성, `week8-solution` → `week8-dongjae` branch 생성 후 작업
    
    ```bash
    git checkout -b week8-solution
    ```
    
    ![Untitled](12%E1%84%80%E1%85%B5%20GitHub%20%E1%84%92%E1%85%A7%E1%86%B8%E1%84%8B%E1%85%A5%E1%86%B8%20%E1%84%80%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%86%AB(%E1%84%8B%E1%85%AE%E1%86%AB%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC)%20ba82a8ff99f34102917434d6156f37ac/Untitled%201.png)
    
    ```bash
    git checkout -b week8-dongjae(본인 이름)
    ```
    
    ![Untitled](12%E1%84%80%E1%85%B5%20GitHub%20%E1%84%92%E1%85%A7%E1%86%B8%E1%84%8B%E1%85%A5%E1%86%B8%20%E1%84%80%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%86%AB(%E1%84%8B%E1%85%AE%E1%86%AB%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC)%20ba82a8ff99f34102917434d6156f37ac/Untitled%202.png)
    
    - **깔끔한 Github 레포지토리를 위해 `week8-dongjae`(본인 이름)에서 origin에 직접 push하는 것을 지양하도록 함 → push는 항상 `week8-solution`과 같은 solution branch에 한하여 진행**
    - **`week8-dongjae`(본인 이름)에서 작업들을 진행할 때마다 commit은 추가함**
    
5. 8주차 코드 작업 중 이런저런 이슈로 7주차에 **변경 요청 사항이 있을 경우** 바로바로 이전 주차 발표자와 논의를 진행
    1. 만약 7주차에서 변경해줘야 할 경우, 변경 사항을 `**week7-solution`에 반영 후 다시 `main` ← `week7-solution` 머지(Pull Request) 진행**
        
        ![Untitled](12%E1%84%80%E1%85%B5%20GitHub%20%E1%84%92%E1%85%A7%E1%86%B8%E1%84%8B%E1%85%A5%E1%86%B8%20%E1%84%80%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%86%AB(%E1%84%8B%E1%85%AE%E1%86%AB%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC)%20ba82a8ff99f34102917434d6156f37ac/Untitled%203.png)
        
        **`week7-solution`**에 바뀐 내용을 **Push**함
        
        ![Untitled](12%E1%84%80%E1%85%B5%20GitHub%20%E1%84%92%E1%85%A7%E1%86%B8%E1%84%8B%E1%85%A5%E1%86%B8%20%E1%84%80%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%86%AB(%E1%84%8B%E1%85%AE%E1%86%AB%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC)%20ba82a8ff99f34102917434d6156f37ac/Untitled%204.png)
        
        이후 Pull Request를 통해 `**main` ← `week7-solution` 머지(Pull Request)**를 진행함
        
         
        
    2. `**week8-solution`을 포함한 각자 branch에서 rebase** 후 그대로 작업 이어서 진행
        
        ```bash
        main에 업데이트 된 내용을 pull 받아
        git switch main
        git pull
        
        이후 week8-solution, week8-dongjae(본인 이름)에서 rebase
        git switch week8-solution
        git rebase main
        
        git switch week8-dongjae(본인 이름)
        git rebase main
        ```
        
        ![Untitled](12%E1%84%80%E1%85%B5%20GitHub%20%E1%84%92%E1%85%A7%E1%86%B8%E1%84%8B%E1%85%A5%E1%86%B8%20%E1%84%80%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%86%AB(%E1%84%8B%E1%85%AE%E1%86%AB%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC)%20ba82a8ff99f34102917434d6156f37ac/Untitled%205.png)
        
6. 8주차 과제 완성본까지 작업이 완료되었다면 `**week8-solution`에 Rebase**한 후 **`main ← week8-solution` 병합(Pull Request)**
    
    ```bash
    week8-dongjae 에서 작업을 진행하며 쌓은 **commit**들을 **week8-solution**에 rebase 해줌
    git switch week8-solution
    git rebase week8-dongjae(본인 이름)
    
    이후 **week8-solution**에서 push
    git push
    ```
    
    **push**한 이후 **pull request**를 통해 **main**에 병합
    
    ![Untitled](12%E1%84%80%E1%85%B5%20GitHub%20%E1%84%92%E1%85%A7%E1%86%B8%E1%84%8B%E1%85%A5%E1%86%B8%20%E1%84%80%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%86%AB(%E1%84%8B%E1%85%AE%E1%86%AB%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC)%20ba82a8ff99f34102917434d6156f37ac/Untitled%206.png)
    
7. 9주차 발표자가 이어서 동일하게 진행

즉, `**-solution**` 레포지토리에는 세미나 완성본이 아닌 **과제 완성본** 코드들이 `**week#-solution**` branch에 담겨있어야 합니다.

이는 12기가 세미나 이후에라도 최대한 세미나 자료를 따라 개발할 수 있도록 하기 위함입니다. 열심히 노력했음에도 과제를 모두 구현하지 못했다면 다음 세미나 진행을 위해 과제 완성본인 `**-solution**` branch만 세미나 이전에 **`-seminar`** 레포지토리의 **`main`** 브랜치에 제공합니다.

**협업 가이드라인**

- 기조 : remote 레포지토리를 깔끔하게 관리하자
    
    ~~(다시 말해 git graph가 이쁘게..)~~
    
1. **git pull 대신 git rebase 사용하기 (권장)**
    1. git pull은 git fetch와 git merge를 수행하는 명령어이기 때문에 git merge를 수행하는 과정에서 merge commit이 불필요하게 생김 (이게 왜 불필요함? 이라고 하면 어쩔 수 없고..) 
        
        ```jsx
        git fetch origin main
        git rebase origin main
        -----------------------
        git pull origin main --rebase
        ```
        
2. **커밋은 몰아서 X 유관된 변경사항들끼리 자주자주 커밋하기**
    - 단 단순 오탈자 수정, 픽셀 단위 수정 등 지나치게 작은 작업 범위의 커밋은 지양
    - 커밋 메시지 템플릿 활용
        - 각 레포지토리에 세팅되어 있음
        - .gitmessage 세팅이 되어있으면 `git add .` → `git commit` → COMMIT_EDITMSG가 생성됨 → COMMIT_EDITMSG 내에서 template에 따라 commit message 작성
    
    .gitmessage.txt
    
    ```python
    # Title: Summary, imperative, don't end with a period
    
    #   feat    : 기능 (새로운 기능)
    #   fix     : 버그 (버그 수정)
    #   refactor: 리팩토링
    #   style   : 스타일 (코드 형식, 세미콜론 추가: 비즈니스 로직에 변경 없음)
    #   docs    : 문서 (문서 추가, 수정, 삭제)
    #   test    : 테스트 (테스트 코드 추가, 수정, 삭제: 비즈니스 로직에 변경 없음)
    #   chore   : 기타 변경사항 (빌드 스크립트 수정 등)
    ```
    
    참고: [https://velog.io/@bky373/Git-커밋-메시지-템플릿](https://velog.io/@bky373/Git-%EC%BB%A4%EB%B0%8B-%EB%A9%94%EC%8B%9C%EC%A7%80-%ED%85%9C%ED%94%8C%EB%A6%BF)
    
    - **커밋 메시지 템플릿 적용방법**
        - 터미널에 아래 명령어를 입력해줍니다.
            
            ```bash
            git config --local commit.template .gitmessage.txt
            ```
            
        - 터미널에 아래 명령어도 입력해줍니다.
            
            ```bash
            git config --local core.editor "code --wait"
            ```
            
        - 이후 아래와 같이 커밋메시지를 양식에 맞춰 적습니다.
            
            ```python
            # Title: Summary, imperative, don't end with a period
            feat: add main.py
            
            #   feat    : 기능 (새로운 기능)
            #   fix     : 버그 (버그 수정)
            #   refactor: 리팩토링
            #   style   : 스타일 (코드 형식, 세미콜론 추가: 비즈니스 로직에 변경 없음)
            #   docs    : 문서 (문서 추가, 수정, 삭제)
            #   test    : 테스트 (테스트 코드 추가, 수정, 삭제: 비즈니스 로직에 변경 없음)
            #   chore   : 기타 변경사항 (빌드 스크립트 수정 등)
            ```
            
        - 저장 후 창을 끄면 자동으로 커밋이 완료 됩니다. 또는, `ctrl + w` 버튼을 눌러 창을 닫습니다.
    
3. **PR 생성**
    1. PR 제목은 “[week8] 주요작업내용”
    2. PR reviewer → 다른 발표자들, assignee → 자신
    3. PR comment에 작업한 내용 간략하게 정리해서 설명해두기
    ex) 프론트엔드 변경사항은 스샷 같이 찍어 올리기, 백엔드 변경사항 중에 모델이 추가되면 어떤 모델이고, 어떤 필드, 종속 관계 있는지 적어주기, 기타 자잘한 수정이면 뭐 바꿨는지 말로 적기
    
    ![Untitled](12%E1%84%80%E1%85%B5%20GitHub%20%E1%84%92%E1%85%A7%E1%86%B8%E1%84%8B%E1%85%A5%E1%86%B8%20%E1%84%80%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%86%AB(%E1%84%8B%E1%85%AE%E1%86%AB%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC)%20ba82a8ff99f34102917434d6156f37ac/Untitled%207.png)
    
    ![Untitled](12%E1%84%80%E1%85%B5%20GitHub%20%E1%84%92%E1%85%A7%E1%86%B8%E1%84%8B%E1%85%A5%E1%86%B8%20%E1%84%80%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%86%AB(%E1%84%8B%E1%85%AE%E1%86%AB%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%8C%E1%85%B5%E1%86%AB%E1%84%8B%E1%85%AD%E1%86%BC)%20ba82a8ff99f34102917434d6156f37ac/Untitled%208.png)
