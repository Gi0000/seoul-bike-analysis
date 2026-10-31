오류 메시지, 원인, 해결 과정
# `UnicodeDecodeError`
- 발생 상황: Pandas로 CSV를 읽을 때 오류 발생
- 오류 메시지: `UnicodeDecodeError`
- 원인: UTF-8 디코더로 파일의 바이트를 해석할 수 없었음.
- 해결 방법: `encoding="euc-kr"` 지정
- 배운 점: CSV를 읽을 때 파일의 문자 인코딩을 확인해야 함.