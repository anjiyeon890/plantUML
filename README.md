#!/bin/bash

# PlantUML 서버 수정 및 재빌드 스크립트

# 클래스 파일을 루트 디렉토리로 이동
echo "Moving class files to the root directory..."
mv BOOT-INF/classes/* .

# 불필요한 디렉토리 삭제
echo "Removing unnecessary directories..."
rm -rf BOOT-INF META-INF

# JAR 파일 재생성
echo "Rebuilding the JAR file..."
jar cf ../plantUMLServer-fixed.jar *

# JAR 파일 내용 확인
echo "Verifying the contents of the new JAR file..."
jar tf ../plantUMLServer-fixed.jar | grep TraceUmlService

echo "PlantUML Server JAR modification and rebuild completed!"
