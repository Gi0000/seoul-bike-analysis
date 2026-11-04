오류 메시지, 원인, 해결 과정
# 데이터 수집 및 구조 파악
## `UnicodeDecodeError`
- 발생 상황: Pandas로 CSV를 읽을 때 오류 발생
- 오류 메시지: `UnicodeDecodeError`
- 원인: UTF-8 디코더로 파일의 바이트를 해석할 수 없었음.
- 해결 방법: `encoding="euc-kr"` 지정
- 배운 점: CSV를 읽을 때 파일의 문자 인코딩을 확인해야 함.
## `TextFileReader`을 DataFrame처럼 다루고 싶을 때
- 발생 상황: `chunksize`를 이용해서 CSV 데이터를 불러왔고, 이의 `shape`를 구하는 과정에서 오류 메시지가 발생함
- 오류 메시지: `'TextFileReader' object has no attribute 'shape'`
- 원인: `TextFileReader`은 데이터를 한 번에 모두 읽지 않고, 지정한 행 수만큼 나누어 읽는 객체.
- 해결 방법: `TextFileReader`타입의 객체를 DataFrame처럼 다루려면 청크를 하나씩 꺼내야 함. 꺼낸 청크는 일반적인 DataFrame임. 따라서 반복문을 통해 데이터를 순환하며 각 청크를 꺼냈음. 
- 배운 점: 반복문에 `enumerate`를 이용하면 편리함.
    - `enumerate()` 함수는 인자로 넘어온 목록을 기준으로 인덱스와 원소를 차례대로 접근하게 해주는 반복자 객체를 반환해주는 함수
    - 기본적으로 인덱스와 원소로 이루어진 튜플을 만들어줌.
