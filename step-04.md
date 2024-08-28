축하합니다! 이제 마지막 단계인 GitHub Pages에 MkDocs 사이트를 배포하는 과정을 진행해보겠습니다. 이 단계를 완료하면, 다른 사람들도 웹에서 직접 문서를 볼 수 있게 됩니다.

### **Step 4: GitHub Pages 배포**

#### 1. GitHub 리포지토리 생성

먼저 GitHub에서 새 리포지토리를 생성해야 합니다.

1. GitHub에 로그인하고, 오른쪽 상단의 `+` 버튼을 클릭한 다음 `New repository`를 선택합니다.
2. 리포지토리 이름을 입력합니다. 예를 들어, `mkdocs-tutorial`로 이름을 지정할 수 있습니다.
3. `Public` 리포지토리로 설정하고, 필요에 따라 `README` 파일을 생성하지 말고, `Create repository` 버튼을 클릭합니다.

#### 2. 로컬 프로젝트와 GitHub 리포지토리 연결

터미널에서 현재 MkDocs 프로젝트 디렉토리에서 GitHub 리포지토리와 연결을 설정합니다.

```bash
git init
git remote add origin https://github.com/yourusername/mkdocs-tutorial.git
```

위의 명령어에서 `yourusername`을 실제 GitHub 사용자 이름으로, `mkdocs-tutorial`을 리포지토리 이름으로 변경하세요.

#### 3. 변경 사항 커밋 및 푸시

이제 로컬 MkDocs 프로젝트의 모든 파일을 GitHub 리포지토리에 커밋하고 푸시합니다.

```bash
git add .
git commit -m "Initial commit"
git push -u origin main
```

이 명령어들은 현재 프로젝트의 모든 파일을 커밋하고, GitHub의 `main` 브랜치에 푸시합니다.

#### 4. GitHub Pages에 배포

MkDocs는 GitHub Pages로 쉽게 배포할 수 있는 기능을 제공합니다. 다음 명령어를 터미널에서 실행하세요:

```bash
mkdocs gh-deploy
```

이 명령어는 자동으로 `gh-pages`라는 브랜치를 생성하고, 이 브랜치에 사이트의 정적 파일을 배포합니다. 배포가 완료되면 터미널에 배포된 사이트의 URL이 표시될 것입니다. 기본적으로 `https://yourusername.github.io/mkdocs-tutorial/`와 같은 형태로 접근할 수 있습니다.

#### 5. GitHub Pages 설정 확인 (선택 사항)

GitHub 리포지토리의 `Settings` 탭에 들어가서 `Pages` 섹션을 확인하세요. 여기에서 사이트의 배포 상태를 확인할 수 있으며, 기본 URL을 수정하거나 커스텀 도메인을 설정할 수도 있습니다.

### 마무리

이제 GitHub Pages에 성공적으로 MkDocs 사이트를 배포했습니다. 다른 사람들과 해당 URL을 공유하면, 누구든지 웹 브라우저에서 문서를 볼 수 있습니다.

모든 과정이 완료되었다면, 추가적으로 궁금한 사항이나 더 다루고 싶은 주제가 있으면 언제든지 알려주세요!
