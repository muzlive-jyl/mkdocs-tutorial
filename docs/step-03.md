> 잘 하셨습니다! 이제 세 번째 단계로 넘어가서 MkDocs 사이트의 테마를 변경하고, 일부 추가적인 커스터마이징을 진행해보겠습니다.

### **Step 3: 테마 변경 및 커스터마이징**

이번 단계에서는 MkDocs 사이트의 테마를 변경하고, 추가적인 설정을 통해 사이트를 더욱 깔끔하게 꾸며보겠습니다.

#### 1. MkDocs 테마 변경

MkDocs는 다양한 기본 테마를 제공합니다. 이 중에서 `material` 테마를 사용해 보겠습니다. `material` 테마는 깔끔하고 현대적인 디자인으로 많이 사용되는 테마입니다.

먼저 `material` 테마를 설치합니다. 터미널에 다음 명령어를 입력하세요:

```bash
pip install mkdocs-material
```

이제 `mkdocs.yml` 파일을 열고, 테마 설정을 추가합니다.

```yaml
site_name: My Project Documentation

theme:
  name: 'material'

nav:
  - Home: index.md
  - Module 1: module1/README.md
  - Module 2: module2/README.md
  - Module 3: module3/README.md
```

이렇게 하면 사이트에 `material` 테마가 적용됩니다.

#### 2. 로고 및 파비콘 설정 (선택 사항)

사이트의 로고와 파비콘을 설정할 수도 있습니다. 예를 들어, 프로젝트의 로고 이미지를 `docs` 폴더에 `logo.png`로 저장하고, 이를 MkDocs 설정에 반영할 수 있습니다.

로고와 파비콘 설정을 추가하려면, `mkdocs.yml` 파일에 다음과 같이 추가합니다:

```yaml
theme:
  name: 'material'
  logo: 'img/logo.png'  # docs 폴더 내의 경로
  favicon: 'img/favicon.ico'  # docs 폴더 내의 경로
```

`img` 폴더는 `docs` 폴더 안에 생성하여 이미지를 저장하면 됩니다. 로고와 파비콘은 선택 사항이므로, 필요하지 않다면 생략해도 됩니다.

#### 3. 푸터 설정

사이트 하단에 표시될 푸터 메시지를 설정할 수 있습니다. 예를 들어, 저작권 정보나 간단한 링크를 추가할 수 있습니다.

`mkdocs.yml` 파일에 다음 내용을 추가해보세요:

```yaml
theme:
  name: 'material'

extra:
  social:
    - icon: fontawesome/brands/github
      link: https://github.com/yourusername/your-repo
    - icon: fontawesome/brands/twitter
      link: https://twitter.com/yourusername

markdown_extensions:
  - toc:
      permalink: true
```

이 설정은 푸터에 GitHub 및 Twitter 링크를 추가하는 예시입니다. 필요에 따라 추가하거나 수정할 수 있습니다.

#### 4. 변경 사항 확인

이제 다시 한 번 MkDocs 서버를 실행하여, 변경된 테마와 커스터마이징이 제대로 적용되었는지 확인해보겠습니다.

```bash
mkdocs serve
```

브라우저에서 새롭게 변경된 테마와 설정을 확인해보세요. 테마가 `material`로 변경되고, 로고나 푸터가 설정대로 잘 표시되는지 확인합니다.

> 이제 마지막 단계로, 문서를 GitHub Pages에 배포하여 다른 사람들도 접근할 수 있게 만들어보겠습니다. 이 단계에 대해 준비가 되면 알려주세요!
