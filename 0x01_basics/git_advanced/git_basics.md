## 0x01. git add
> **Effect:** Moves files from *untracked* to *staged* (changes to be committed).
#### 1.1 when and why
- `commit` 전 단계로, 파일을 `untracked` ➡️ `tracked` 상태로 변경.
- 버전 관리를 위해 작업 파일을 나누어서 관리 가능.
  - Allows granular version control by committing specific changes separately.
  - Enhances flexibility in managing versions, making it easier to group related changes.
- 굳이 따로따로 add를 거치는 이유는 버전관리때문이다. 현재 작업중인것들을 각각 나눠서 따로따로 commit을 해주고 올리고 싶을때 사용한다. add를 해줘야만 commit의 대상으로 들어가기 때문에 현재 작업중인 것들중에서 같은버전으로 묶고 싶은것들을 다 add해준다음, commit을 하고, 다른 버전으로 해주고 싶은 것들을 나눠서 add-commit의 과정을 거침으로서 버전을 분리 할 수 있는 것이다. 하지만 일반적으로는 굳이 이렇게 나눠서 작업하지는 않고 git add .을 통해서 한꺼번에 add를 해준다.

#### 1.2 usage
1. Add a specific file:  
     ```bash
     git add <filename>
     ```
2. Add all changes in the directory:  
     ```bash
     git add .
     ```
- 

3. Undoing an add:
```bash
git rm --cached <filename>
```

## 0x02. git commit
> commit을 함으로써 git에 저장을 한다. 또한 git에 저장을 함으로써 코드를 삭제, 변경하더라도 다시 이전의 상태로 되돌릴수가 있게 된다. 
#### 2.1 when and why
- Save changes in the repository
  - Saves your work and its history at a specific point in time.
- Allows flexibility to modify, delete, or revert code changes as needed.

#### 2.2 usage
1. Open the editor to write a commit message:  (vim으로 보통 바로 들어감)
     ```bash
     git commit
     ```
2. Commit with a message directly:  
     ```bash
     git commit -m "Commit message"
     ```

#### 2.3 git add & commit
|untracked|add : untracked -> tracked |commit|
|---|---|---|
|새 파일|add로 commit 준비 완료|git에 저장완료|
