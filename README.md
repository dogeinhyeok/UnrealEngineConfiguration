# 언리얼 엔진 프로젝트 설정 파일

언리얼 엔진 5.6 기반의 프로젝트에서 사용되는 설정값들을 다른 프로젝트에 적용할 수 있도록 정리한 것입니다.

1. [Unreal Clangd 설정하기](#unreal-clangd-설정하기)
2. 이 프로젝트의 모든 파일들을 프로젝트 루트 폴더에 덮어 쓰기

---

# LyraStarterGame 프로젝트

LyraStarterGame은 언리얼 엔진 학습을 위한 통합 템플릿 프로젝트입니다. 이 프로젝트는 언리얼 엔진 5.6 버전을 기반으로 개발되었습니다.

## 프로젝트 개요

LyraStarterGame은 언리얼 엔진의 다양한 기능과 실전 사용법을 체계적으로 익힐 수 있도록 설계되었습니다. 초보자부터 중급자까지 단계별로 따라갈 수 있는 실습 중심의 구조를 채택하여, 실제 게임 개발에 필요한 핵심 역량을 효과적으로 쌓을 수 있습니다.

### Visual Studio로 개발하기

#### 필수 확장 프로그램 설치하기

Workloads 아래 Game development with C++와 다음 옵션을 선택합니다.

- .NET desktop development
- Desktop development with C++
- Universal Windows Platform development
- Game development with C++
  - Unreal Engine installer

#### Visual Studio 프로젝트 생성하기

1. 프로젝트 폴더에서 `LyraStarterGame.uproject` 파일을 마우스 오른쪽 버튼으로 클릭합니다.
2. `Generate Visual Studio project files` 메뉴를 선택합니다.
3. 새로 생성된 `LyraStarterGame.sln` 솔루션 파일을 엽니다.

#### Visual Studio에서 프로젝트 실행하기

1. 솔루션 구성을 `Development Editor`로 설정합니다.
2. 솔루션 플랫폼을 `Win64`로 설정합니다.
3. 솔루션 탐색기에서 LyraStarterGame 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 `디버그 > 새 인스턴스 시작`을 선택합니다.

### VSCode로 개발하기

#### 필수 확장 프로그램 설치하기

- [C/C++ Extension Pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools-extension-pack)
- [C# Dev Kit](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csdevkit)
- [.NET SDK](https://dotnet.microsoft.com/ko-kr/download)

#### Visual Studio Code 프로젝트 생성하기

1. 프로젝트 폴더에서 `LyraStarterGame.uproject` 파일을 마우스 오른쪽 버튼으로 클릭합니다.
2. `Generate Visual Studio Code project files` 메뉴를 선택합니다. (없을 경우 언리얼 에디터 환경설정에서 기본 소스 코드 에디터를 VSCode로 변경하세요)
3. VSCode에서 `File > Open Folder`를 선택하고 LyraStarterGame 프로젝트 폴더를 엽니다.

#### Visual Studio Code에서 프로젝트 실행하기

1. VSCode에서 실행 및 디버그 탭을 클릭합니다 (Ctrl+Shift+D).
2. 실행 및 디버그 드롭다운에서 `Launch LyraStarterGame (Development)`를 선택합니다.
3. 실행 버튼을 클릭합니다.

#### Visual Studio Code 또는 Visual Studio로 코드 수정 및 실행하기

1. 언리얼 엔진 에디터에서 `Edit > Editor Preferences > Live Coding > Enable Live Coding`을 비활성화합니다.
2. Visual Studio 또는 VSCode에서 코드를 수정하고 저장합니다 (Ctrl+S).
3. 코드를 컴파일합니다:
   - **언리얼 에디터**: 에디터 내에서 `컴파일` 버튼(⟳) 클릭
   - **Visual Studio**: 솔루션 빌드(F7) 또는 `빌드 > 솔루션 빌드` 메뉴 선택
   - **Visual Studio Code**: 명령 팔레트(Ctrl+Shift+P)에서 `Tasks: Run Build Task` 실행
4. 코드 인텔리센스가 제대로 적용되도록 프로젝트를 새로고침합니다:
   - **Visual Studio**: 언리얼 에디터에서 `Tools > Refresh Visual Studio Project` 클릭
   - **Visual Studio Code**: 언리얼 에디터에서 `Tools > Refresh Visual Studio Code Project` 클릭
5. 언리얼 에디터에서 `Play` 버튼을 클릭하여 레벨을 실행하고 변경 사항을 테스트합니다.

### Cursor로 개발하기

https://www.youtube.com/watch?v=9Km1GyYCnh4 참고

#### 필수 확장 프로그램 설치하기

기존의 C/C++, C# 확장 프로그램을 제거하고 다음 확장 프로그램을 설치합니다. Microsoft C/C++, C# 확장 프로그램과 충돌할 수 있습니다.

- [AnySphere C/C++ Tools](https://marketplace.cursorapi.com/items/?itemName=anysphere.cpptools)
- [AnySphere C# Tools](https://marketplace.cursorapi.com/items/?itemName=anysphere.csharp)
- [clangd](https://marketplace.cursorapi.com/items/?itemName=llvm-vs-code-extensions.vscode-clangd)

#### Unreal Clangd 설치하기

clangd는 C/C++ 코드의 자동완성, 문법 검사, 오류 표시, 함수 정의로 이동 등을 제공하는 언어 서버입니다. unreal-clangd는 언리얼 엔진 프로젝트에 특화된 clangd 설정을 자동으로 생성해주는 확장 프로그램입니다.

1. https://github.com/boocs/unreal-clangd 접속하기
2. Releases 탭에서 `unreal-clangd-x.x.x.vsix` 파일을 다운로드받습니다.
3. Cursor에서 `Extensions` 탭에 다운로드 받은 파일을 드래그 앤 드롭하여 설치합니다.

#### LLVM 설치하기

LLVM은 clang, clang++, clangd, lld 등 여러 도구들을 포함한 전체 컴파일러 인프라스트럭처입니다. LLVM을 설치해야 clangd를 사용할 수 있습니다.

1. https://releases.llvm.org 접속하기
2. 언리얼 엔진 버전에 맞는 LLVM 파일을 다운로드받습니다. (언리얼 엔진 5.6 버전인 경우 18.1.8 버전을 다운로드받습니다.)
3. `LLVM-18.1.8-win64.exe` 파일을 실행하여 설치합니다.
4. 안내에 따라 설치합니다. system path는 `Add LLVM to the system PATH for all users` 옵션을 선택합니다.
5. `Ctrl + Shift + P`를 눌러 명령 팔레트를 열고 `Developer: Reload Window` 명령을 실행하여 설치를 완료합니다.

#### Unreal Clangd 설정하기

1. 일반 폴더가 아닌 .code-workspace 파일을 Cursor로 열어야 합니다.
2. `Ctrl + Shift + P`를 눌러 명령 팔레트를 열고 `unreal-clangd: Create Unreal clangd project` 명령을 실행하여 설정을 완료합니다.
3. install type 팝업 메시지에서 `Full`을 선택합니다.
4. 자동으로 재시작되며 반응이 없으면 2번을 다시 실행합니다.
5. clangd 실행 파일 위치(`C:\Program Files\LLVM\bin\clangd.exe`)를 선택합니다.
6. Visual Studio 설치 시 선택한 MSVC Tool 버전(`Windows 11 SDK 10.0.22621.0`)을 선택합니다.
7. `Source` 폴더에 있는 cpp 파일을 열어보면 코드 인텔리센스가 제대로 적용되는 것을 확인할 수 있습니다.
8. 코드 줄 위에 마우스를 올렸을 때 해당 줄에 대한 팝업이 뜨면 성공입니다.
9. 하단을 통해 인덱싱 진행 사항을 확인할 수 있으며, 시간이 오래 걸릴 수 있습니다.

#### UE-Clang-Format 설정하기

1. [이 사이트](https://github.com/TensorWorks/UE-Clang-Format/blob/main/.clang-format)에서 .clang-format 파일을 다운로드받습니다.
2. `.clang-format` 파일을 프로젝트 루트 폴더에 복사합니다.

#### Cursor에서 코드 수정 및 실행하기

Microsoft는 2024년부터 비공식 Visual Studio 제품에서 자신들의 C/C++ 및 C# 확장 프로그램 사용을 금지했습니다. Cursor는 Microsoft의 공식 Visual Studio Code가 아니므로 직접적인 빌드 및 실행은 불가능합니다.

1. 언리얼 에디터에서 `.uproject` 파일을 열어 프로젝트를 시작합니다.
2. Cursor에서 소스 코드를 편집하고 저장합니다 (Ctrl+S).
3. 언리얼 에디터에서 컴파일 버튼(⟳)을 클릭하여 변경사항을 적용합니다.
4. 언리얼 에디터에서 Play 버튼을 클릭하여 실행합니다.

## 개발 환경

- 언리얼 엔진 5.6
- Visual Studio 2022
- Visual Studio Code
- Cursor(빌드 및 실행 불가)
- Windows 10/11

## 프로젝트 구조

- **Source/**: C++ 소스 코드
- **Content/**: 블루프린트, 에셋, 레벨 등 콘텐츠
- **Config/**: 프로젝트 설정 파일

## 문서화 규칙

자세한 코드 주석 및 문서화 규칙은 `.cursor/rules/` 폴더를 참조해주세요.

## 기여하기

1. 프로젝트를 포크합니다.
2. 새로운 브랜치를 생성합니다.
3. 변경사항을 커밋합니다.
4. 브랜치에 푸시합니다.
5. Pull Request를 제출합니다.
