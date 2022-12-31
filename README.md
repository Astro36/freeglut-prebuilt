# FreeGLUT Prebuilt Library

## Usage

### Visual Studio 2022

1. 해당 저장소의 디렉토리를 프로젝트 폴더로 **복사**합니다.

    ```
    my-project
      freeglut
        bin
        include
        lib
      include
      src
      project.sln
      project.vcxproj
      ...
    ```

    > Git [서브모듈](https://git-scm.com/book/ko/v2/Git-도구-서브모듈)을 이용하면 버전 관리를 편리하게 할 수 있습니다.
    >
    > ```
    > $ git submodule add https://github.com/Astro36/freeglut-prebuilt.git freeglut
    > ```

2. `project > 속성 > 디버깅 > 환경`으로 이동해 아래와 같이 환경 변수를 **지정**합니다.

    | Win32(x86) | x64 |
    | --- | --- |
    | ![image](https://user-images.githubusercontent.com/10459262/210139392-91b2af64-e998-49d0-9275-a2ac7a36d299.png) | ![image](https://user-images.githubusercontent.com/10459262/210139398-a20a3501-8389-444d-9db6-5f43c10ca098.png) |
    | `PATH=freeglut\bin\x86;%PATH%` | `PATH=freeglut\bin\x64;%PATH%` |

    지정한 환경변수는 `project.vcxproj.user` 파일에 저장됩니다.

    GitHub에서 제공하는 Visual Studio `.gitignore` 프리셋에는 `*.vcxproj.user`가 **제외**되어 있으므로, 다른 사람에게 솔루션을 **공유**해야 할 때는 `project.vcxproj.user`가 저장소에 제대로 **업로드** 되었는지 **확인**해야 합니다. 

3. `project > 속성 > VC++ 디렉터 > 포함 디렉터리`으로 이동해 아래와 같이 경로를 **추가**합니다.

    | 모든 플랫폼 |
    | --- |
    | ![image](https://user-images.githubusercontent.com/10459262/210139533-88bc27e0-601b-413a-93ea-ab3fa9142862.png) |
    | `freeglut\include;` |

4. `project > 속성 > VC++ 디렉터 > 라이브러리 디렉터리`으로 이동해 아래와 같이 경로를 **추가**합니다.

    | Win32(x86) | x64 |
    | --- | --- |
    | ![image](https://user-images.githubusercontent.com/10459262/210139612-2dc24c35-7d90-4de8-8e53-c5c543ff2e85.png) | ![image](https://user-images.githubusercontent.com/10459262/210139623-bb2e06a5-674a-4548-9fbe-81faf59d6ee1.png) |
    | `freeglut\lib\x86;` | `freeglut\lib\x64;` |
