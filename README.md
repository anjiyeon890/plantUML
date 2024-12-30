README
PlantUML 서버 수정 및 재빌드 가이드
이 문서는 plantUMLServer-fixed.jar 파일의 클래스 파일을 루트 디렉토리로 이동하고, 불필요한 디렉토리를 제거하여 수정 및 재빌드하는 방법을 설명합니다.

JAR 수정 및 재빌드 단계
클래스 파일 이동
BOOT-INF/classes/ 디렉토리에 있는 모든 클래스 파일을 루트 디렉토리로 이동합니다:

bash
코드 복사
$ mv BOOT-INF/classes/* .
불필요한 디렉토리 삭제
BOOT-INF와 META-INF 디렉토리를 삭제하여 구조를 정리합니다:

bash
코드 복사
$ rm -rf BOOT-INF META-INF
JAR 파일 재생성
수정된 구조로 JAR 파일을 다시 생성합니다:

bash
코드 복사
$ jar cf ../plantUMLServer-fixed.jar *
내용 확인
재생성된 JAR 파일에 필요한 파일이 포함되어 있는지 확인합니다. 예:

bash
코드 복사
$ jar tf plantUMLServer-fixed.jar | grep TraceUmlService
예상 결과:

bash
코드 복사
com/neo/plantUMLServer/service/TraceUmlService.class
추가 참고 사항
스프링 빈(Spring Bean)을 사용하지 않고 가져온 경우, 추가 설정이 필요할 수 있습니다.
위 과정을 통해 PlantUML 서비스는 정상적으로 사용할 수 있습니다.
