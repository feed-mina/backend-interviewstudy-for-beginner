

### ./gradlew run --debug 와 gradle --debug의 차이
### Gradle Wrapper VS 로컬 설치된 Gradle
#### ./gradlew run --debug 이 명령은 Gradle Wrapper를 사용하여 프로젝트를 빌드하고 실행합니다. Gradle Wrapper는 프로젝트 디렉토리 내에 포함된 Gradle 버전을 사용하여 빌드를 수행한다. 
#### gradle --debug : 이 명령은 로컬 시스템에 설치된 Gradle을 사용하여 빌드를 실행한다. 따라서 시스템에 Gradle이 설치되어 있어야 한다.

#### ./gradlew run --debug 명령은 프로젝트의 Gradle Wrapper 스트립트를 실행하여 빌드를 수행한다. Gradle Wrapper를 사용하면 프로젝트에 Gradle를 설치하지 않고도 Gradle 빌드를 실행할 수 있다. ./gradlew run --debug`는 Gradle Wrapper를 사용하여 프로젝트를 빌드하는 데 반해 `gradle --debug`는 시스템에 설치된 Gradle을 사용한다.


### gradlew.bat 와 gradlew
#### gradlew 및 gradlew.bat은 Gradle을 프로젝트 내에 포함시켜 프로젝트를 빌드하는 스크립트 파일이다. 이 파일들은 Gradle Wrapper를 사용하여 프로젝트를 빌드하고 Gadle을 설치하지 않은 상태에서도 Gradle 빌드 도구를 사용할 수 있도록 한다.
#### gradlew : Unix 또는 리눅스 기반 시스테멩서 사용되는 Gradle Wrapper 스크립트이다. 이 스크립트는 Batch 파일로 작성되어 있으며 windows 환경에서 프로젝트를 빌드할때 사용된다.

#### Gradle Wrapper는 프로젝트 디렉토리에 포함된 Gradle 비전을 사용하여 프로젝트를 빌드하므로 개발자가 직접Gradle을 설치하거나 관리할 필요가 없다. 대신에 프로젝트 디렉토리 내에 gradlew 또는 gradlew.bat 파일을 실행하여 Gadle 빌드를 수행할 수 있다. Gradle Wrapper는 프로젝트의 Gradle 비전을 제어하기 위해 gradle-wrapper.properties 파일과 함께 사용된다.

#### build.gradle 파일은 Gradle 빌드 스크립트 파일로 프로젝트 빌드 구성을 정의하는데 사용된다. 이 파일은 Gradle빌드 도구가 프로젝트를 빌드하는 데 필요한 모든 정보를 포함하고 있다. 

플로거인 적용 : 프로젝트에서 사용할 Gradle 플러그인을 적용한다. 예를 들어 Java 프로젝트를 빌드할때는 'java' 플로그인을 적용한다.

의존성 설정 : 프로젝트가 의존한는 외부 라이브러니나 모듈에 대한 정보를 정의한다. 의존성은 Maven Central Repository, Jcenter 등의 리포지토리에서 가져 올 수 있다.
빌드 구성 : 빌드 동작을 정의한다. 컴파일, 테스트진행, 피키징 등의 작업을 설정할 수 있다. 빌드 결과물의 경로,빌드 옵션 등을 지정할 수 있다.






























