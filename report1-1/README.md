`package.json` 에 대해 작성하세요.

# 1. Description
`package.json`은 `npm`을 통해 설치한 패키지의 버전 및 의존성(dependencies)을 관리하는 문서입니다. package.json을 작성할 때에는 JavaScript의 객체 리터럴이 아니라 올바를 JSON 형식이어야 합니다.

이 문서의 많은 부분은 `npm-config`에 쓰여있는 설정에 영향을 받습니다.


> **npm : Node Package Manager**
> 대부분의 자바스크립트 프로그램은 패키지라는 이름으로 npm에 등록되어 있으므로, 특정 기능의 패키지가 필요하면 npm에서 찾아 설치하면 됩니다. npm에는 60만 개 이상의 패키지가 등록되어있습니다.



# 2. pakage.json 주요 속성

### name
`package.json` 에서 가장 중요한 항목은 `name`과 `version` 입니다. `name`과 `version`을 통해 각 패키지의 고유성을 판별하게 됩니다. 이름을 지정하기 위해서는 아래의 규칙을 준수해야 합니다.

몇 가지 규칙 :
- 이름은 **214**자 이내여야 합니다.
- 반드시 **소문자**로 작성해야 합니다.
- 점(.)이나 밑줄(_)로 시작할 수 없습니다.
- URL이나 Command Line의 인수이며 폴더명으로 사용됩니다.

### version
노트 패키지의 버전은 [SemVer](https://docs.npmjs.com/misc/semver)의 규칙을 엄격히 준수해야합니다. `[메이저].[마이너].[패치]` 세 자리로 이루어져 있습니다. 메이저는 업데이트(이전 버전과 호환 불가능), 마이너는 소규모 업데이트(이전 버전과 호환 가능), 패치는 버그 수정 시에 버전을 올립니다. 패키지의 내용을 변경하려면 version을 변경해야만 합니다.

### description
사용자가 `npm search`에 검색하였을 때 표시되는 설명입니다.

### keywords
npm search 사용 시 도움이 됩니다. 패키지의 키워드를 배열로 지정할 수 있습니다.

### homepage
프로젝트 홈페이지로 연결되는 **URL**을 지정합니다.
```JSON
"homepage": "https://github.com/owner/project#readme"
```

### bugs
패키지에 문제가 있을 때 사용자에게 도움을 주기 위해 사용합니다. 이슈 트래킹을 볼 수 있는 URL 및 이메일 주소를 지정할 수 있습니다.
```JSON
{ "url" : "https://github.com/owner/project/issues"
, "email" : "project@hostname.com"
}
```

### license
패키지 사용을 허용하는 방법과 제한 사항을 알 수 있도록 라이센스를 지정할 수 있습니다.
```JSON
{ "license": "(MIT OR Apache-2.0)" }
```

### people fields : author, contributor
`author`는 한 사람만을 지정하고, `contributor`는 여러 사람을 배열로 지정할 수 있습니다. 
```JSON
{ "name" : "Barney Rubble"
, "email" : "b@rubble.com"
, "url" : "http://barnyrubble.tumblr.com/"
}
```

### files
패키지가 의존성으로 설치될 때 같이 포함될 파일들의 배열입니다.
`.npmignore`라는 파일을 패키지의 루트 혹은 하위 폴더에 생성하여 대상에서 제외할 수 있습니다.

### main
프로그램의 기본 시작점(entry point)이 되는 모듈의 ID입니다.

### repository
소스 코드가 관리되는 저장소의 위치를 지정합니다.
```JSON
"repository": {
  "type" : "git",
  "url" : "https://github.com/npm/cli.git"
}
```

### script
패키지 생명 주기 중 다양한 타이밍에서 실행되는 스크립트 명령을 포함하고 있는 사전입니다. 여러가지 npm 명령어를 알려줍니다. **npm start**를 사용하면 node server/index.js라는 명령어가 실행됩니다. 그밖에 publish, uninstall, start, restart, test, version 등이 있습니다. 뿐만 아니라 임의로 script를 만들수 있습니다.

### dependencies
패키지의 배포 시 포함될 의존성 모듈을 지정합니다.

### devDependencies
패키지의 테스트 관련 모듈이나 트랜스 파일러 관련 모듈 등 개발 시 사용될 의존성 모듈을 지정합니다. 배포 시 포함되지 않습니다.

### peerDependencies
패키지의 호환성 모듈을 지정합니다.

### bundledDependencies
패키지를 게시할 때 번들로 묶을 패키지 이름을 배열로 지정합니다.

### engines
패키지가 작동하는 node 버전을 지정할 수 있습니다.

### private
개인 저장소의 우연한 발행을 방지하기 위해 npm에서 패키지의 공개 여부를 지정합니다.


# 3. 주요 명령어

### package.json 생성
npm init 명령을 통해 package.json 을 쉽게 생성할 수 있다. 모든 값을 기본값으로 채우고 싶다면 -yes(또는 -y) 옵션을 사용할 수 있다.
```javascript
npm init [--yes]
```

### package.json에 의존성 모듈 정보 자동 추가
모듈 설치 시 --save 옵션을 주면 package.json에 자동으로 업데이트 됩니다.
```javascript
npm install --save {package name}
```

### 글로벌 설치
-g 옵션으로 패키지를 시스템 디렉토리에 설치하여 전역으로 사용할 수 있습니다.
```javascript
npm install -g {package name}
```

### 제거
주의할 점은 --save 나 --save-dev 옵션을 사용해 의존성을 명시한 패키지들은 제거할 때도 --save 나 --save-dev 를 사용해야 package.json 의 의존성 항목을 제거한다.
```javascript
npm uninstall {package name}  [--save--dev|--save|--global]
```

### 업데이트
```javascript
npm update {package name} 
```

### 도움말
```javascript
npm help
```

#### [package.json 공식 문서](https://docs.npmjs.com/files/package.json)

