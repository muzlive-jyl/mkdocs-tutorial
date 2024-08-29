## Step 5: 문서를 예쁘게 꾸미는 방법

MkDocs 사이트를 더 예쁘고 사용하기 쉽게 꾸미는 몇 가지 방법을 소개하겠습니다.

### 1. **상단에 GitHub 원본 링크 추가하기**

MkDocs 사이트 상단에 원본 GitHub 리포지토리로 연결되는 링크를 추가하는 방법을 설명드리겠습니다. 이 링크는 사용자가 문서의 원본 코드나 프로젝트를 쉽게 찾을 수 있도록 도와줍니다.

`mkdocs.yml` 파일에서 `repo_url`과 `repo_name` 설정을 추가하여 GitHub 리포지토리 링크를 표시할 수 있습니다.

```yaml
site_name: My Project Documentation

...

repo_url: https://github.com/muzlive-jyl/mkdocs-tutorial
repo_name: Mkdocs-Tutorial

```

- **`repo_url`**: GitHub 리포지토리의 URL을 설정합니다. 위의 예에서는 `https://github.com/{yourusername}/{repositoryname}`로 설정되어 있습니다. 이 URL을 실제 GitHub 리포지토리의 주소로 변경하세요.
- **`repo_name`**: 링크에 표시될 텍스트를 설정합니다. 예를 들어, "GitHub"로 설정하면, 상단에 "GitHub"이라는 이름으로 링크가 나타납니다.

이 설정을 추가하고 다시 MkDocs 서버를 실행하거나 `mkdocs serve` 명령어로 확인해보면, 상단에 GitHub 리포지토리로 연결되는 링크가 추가된 것을 볼 수 있습니다.

### **2. 테마 색상 커스터마이징**

Material 테마에서는 기본 색상을 변경하여 사이트의 분위기를 바꿀 수 있습니다. `mkdocs.yml` 파일에 다음과 같은 색상 설정을 추가해보세요:

```yaml
theme:
  name: 'material'
  palette:
    primary: 'indigo'
    accent: 'pink'
```

여기서 `primary`는 주요 색상을, `accent`는 강조 색상을 정의합니다. 다른 색상 옵션을 사용해보면서 원하는 스타일을 찾을 수 있습니다.

### 3. Material 테마에서 제공하는 커스터마이징

[docs](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/)

```yml title="mkdocs.yml"
markdown_extensions:
  - pymdownx.highlight:
      anchor_linenums: true
      line_spans: __span
      pygments_lang_class: true
  - pymdownx.inlinehilite
  - pymdownx.snippets
  - pymdownx.superfences
```

#### **문서 내 코드 블록 꾸미기**

코드 블록을 문서에 삽입할 때, 강조된 언어 구문을 사용하여 코드의 가독성을 높일 수 있습니다. 예를 들어, 다음과 같이 코드를 작성할 수 있습니다:

```python title="파이뜬"
def hello_world():
    print("Hello, world!")
```

```swift title="수입푸드"
func helloWorld() {
    print("Hello, world!")
}
```

이렇게 하면 Python 코드 블록이 구문 강조되어 보기 좋게 표시됩니다.

#### 코드 블록에 copy 기능 추가

코드를 복사하는 버튼 기능을 추가할 수 있습니다. `mkdocs.yml` 파일에 다음과 같이 `feature`에 `content.code.annotate` 설정을 추가해보세요:

```yml
theme:
  name: 'material'
  features:
    - content.code.copy
```

#### 코드 블럭 그룹핑
```yml
markdown_extensions:
  - pymdownx.superfences
  - pymdownx.tabbed:
      alternate_style: true
```

=== "C"

    ``` c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```

### 4. **표와 이미지 추가**

Markdown을 사용하여 표와 이미지를 문서에 추가할 수 있습니다. 표는 다음과 같이 작성할 수 있습니다:

```markdown
| Column 1 | Column 2 |
|----------|----------|
| Item 1   | Item 2   |
| Item 3   | Item 4   |
```

| Column 1 | Column 2 |
|----------|----------|
| Item 1   | Item 2   |
| Item 3   | Item 4   |

이미지는 다음과 같이 추가합니다:

```markdown
![Alt text](path/to/image.png)
```
![Immmmmaaagggeee](img/logo.png)

> `img/logo.png`는 이미지 파일의 경로로, `docs` 폴더 안에 이미지를 저장하고 그 경로를 지정해주면 됩니다.

### 5. **Google Analytics 연동**

사이트 방문자 수를 추적하기 위해 Google Analytics를 연동할 수 있습니다. `mkdocs.yml`에 다음과 같은 설정을 추가합니다:

```yaml
extra:
  analytics:
    - 'UA-XXXXXXX-X'  # Google Analytics Tracking ID
```

Google Analytics의 Tracking ID를 위 설정에 넣으면, 사이트 방문자 데이터를 추적할 수 있습니다.

### 6. **폰트 및 아이콘 추가**

Material 테마에서는 Google Fonts나 FontAwesome 아이콘을 쉽게 사용할 수 있습니다. `mkdocs.yml` 파일에 다음과 같은 설정을 추가해 보세요:

```yaml
extra:
  font:
    text: 'Roboto'
    code: 'Roboto Mono'
  icon:
    logo: material/language-python
```

이 설정은 사이트의 텍스트와 코드에 사용할 폰트를 지정하고, 상단 로고에 아이콘을 추가합니다.

### 7. **플러그인 사용**

MkDocs에서는 다양한 플러그인을 사용하여 기능을 확장할 수 있습니다. 예를 들어, `search` 플러그인을 사용하여 사이트 내 검색 기능을 활성화할 수 있습니다.

```yaml
plugins:
  - search
```

이 외에도 다양한 플러그인이 있으니 필요에 따라 추가하면 좋습니다.

이러한 방법들을 통해 MkDocs 사이트를 더 예쁘고 사용자 친화적으로 꾸밀 수 있습니다. 각 설정을 적용한 후, `mkdocs serve` 명령어로 결과를 확인하며 원하는 스타일로 커스터마이징해보세요. 추가적인 질문이 있거나 특정 부분에 대해 더 알고 싶다면 언제든지 말씀해 주세요!
