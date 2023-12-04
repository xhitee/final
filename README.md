# final
#include <stdio.h>

int main() {
    FILE *source, *destination;
    char ch;

    // 소스 파일 열기
    source = fopen("f1.txt", "r");
    if (source == NULL) {
        printf("소스 파일을 열 수 없습니다.");
        return 1;
    }

    // 대상 파일 열기
    destination = fopen("f2.txt", "w");
    if (destination == NULL) {
        printf("대상 파일을 열 수 없습니다.");
        fclose(source);  // 열었던 소스 파일 닫기
        return 1;
    }

    // 소스 파일에서 문자를 읽어 대상 파일에 쓰기
    while ((ch = fgetc(source)) != EOF) {
        fputc(ch, destination);
    }

    // 파일 닫기
    fclose(source);
    fclose(destination);

    printf("파일이 복사되었습니다.");
    return 0;
}
---------------------30점
