> 잘 하셨습니다! 이제 세 번째 단계로 넘어가서 MkDocs 사이트의 테마를 변경하고, 일부 추가적인 커스터마이징을 진행해보겠습니다.

### **Step 2: 문서 작성 및 프로젝트 구조 설정**

이번 단계에서는 각 모듈에 대한 문서를 작성하고, 이를 MkDocs 사이트에 반영하는 과정을 진행할 것입니다.

#### 1. 디렉토리 구조 설정

먼저, 각각의 모듈에 대한 문서를 작성할 디렉토리를 만들어보겠습니다. `docs/` 폴더 안에 새로운 디렉토리를 생성하고, 각 디렉토리에 `README.md` 파일을 만들어 보세요.

다음 명령어를 터미널에 입력하세요:

```bash
mkdir docs/module1 docs/module2 docs/module3
touch docs/module1/README.md docs/module2/README.md docs/module3/README.md
```

이 명령어는 `docs` 폴더 안에 `module1`, `module2`, `module3`이라는 폴더를 생성하고, 각각의 폴더 안에 `README.md` 파일을 만듭니다.

#### 2. 샘플 문서 작성

각 모듈의 `README.md` 파일에 간단한 내용을 작성해보겠습니다. 다음 내용을 각 파일에 복사해서 넣어주세요.

- `docs/module1/README.md`:

```markdown
# Module 1

This is the documentation for **Module 1** of the Xcode Workspace.
```

- `docs/module2/README.md`:

```markdown
# Module 2

This is the documentation for **Module 2** of the Xcode Workspace.
```

- `docs/module3/README.md`:

```markdown
# Module 3

This is the documentation for **Module 3** of the Xcode Workspace.
```

#### 3. `mkdocs.yml` 파일 수정

이제 MkDocs 설정 파일인 `mkdocs.yml`을 열고, 새로 만든 모듈 문서들을 내비게이션 메뉴에 추가해보겠습니다.

`mkdocs.yml` 파일을 열어서, 다음과 같이 수정하세요:

```yaml
site_name: My Project Documentation

nav:
  - Home: index.md
  - Module 1: module1/README.md
  - Module 2: module2/README.md
  - Module 3: module3/README.md
```

이 설정은 사이트의 내비게이션 메뉴에 `Module 1`, `Module 2`, `Module 3` 항목을 추가합니다.

#### 4. 변경 사항 확인

모든 설정을 마쳤다면, 다시 한번 MkDocs 서버를 실행하여 변경 사항을 확인해보겠습니다.

```bash
mkdocs serve
```

브라우저에서 로컬 서버 주소로 접속하여 새로 추가된 모듈 페이지들이 내비게이션 메뉴에 잘 표시되는지 확인하세요. 각 메뉴를 클릭했을 때 해당 모듈의 문서가 올바르게 표시되어야 합니다.

> 이 단계까지 완료하셨다면 다음 단계로 넘어가서 사이트의 테마 변경과 추가적인 커스터마이징을 진행하겠습니다. 완료되면 알려주세요!
