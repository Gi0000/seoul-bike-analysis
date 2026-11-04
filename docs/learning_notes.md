새로운 Python 개념과 활용 방법
# 데이터 정제 및 가공
## `Path` 클래스
- 문제: CSV 파일을 절대경로로 지정해서 관리하고 있었음
- 새롭게 알게 된 점: `Path` 객체는 경로를 조합하고, 파일 존재 여부 및 확장자 등을 확인하는 기능을 제공함.
- 활용 방법:
    - `rental_log_path = Path("../data/raw/bike_rental_log_2601.csv")`
    - `rental_log_path.exists()`

## `chunksize`: pandas가 CSV 데이터를 지정한 행 개수 단위로 나누어 읽도록 하는 매개변수
- 문제: CSV 데이터를 `nrows`를 통해 불러오고 있었음. 이 방법은 메모리가 많이 필요할 때 부적합
- 새롭게 알게 된 점:
    -   | 매개변수 | 역할 |
        | --- | --- |
        | `nrows=10000` | 처음 10,000행만 읽음 |
        | `chunksize=10000` | 데이터를 10,000행씩 나누어 순차적으로 읽음 |
    - `chunksize`를 사용하면 `pd.read_csv()`가 DataFrame 하나를 반환하는 것이 아니라 `TextFileReader` 객체를 반환
- 활용 방법: `pd.read_csv(파일 경로, chunksize = 행 수)`

## 실행 시간을 측정하는 세 가지 방법
| 방법 | 특징 | 추천 상황 |
| --- | --- | --- |
| `time.perf_counter()` | 시작·종료 시간을 직접 기록 | 일반 Python 프로그램 |
| `%time` / `%%time` | 실행 시간을 한 번 측정 | Jupyter Notebook |
| `%timeit` / `%%timeit` | 여러 번 반복 측정 | 코드 성능 비교 |
- 문제: `time.perf_counter()`를 이용해서 시작 시간과 끝 시간의 차이를 구하는 방법 말고 함수를 이용해서 구하는 방법을 찾아봄.
- 활용 방법:  
    - `%%time`: 가장 간단한 방법
        - Jupyter Notebook 셀의 첫 번째 줄에 `%%time`을 작성하면 해당 셀의 실행 식간을 측정
        - `%time`은 한 줄, `%%time`은 셀 전체를 측정
    - `%%timeit`: 반복 측정
        - 코드를 여러 번 실행하고 결과를 통계적으로 요약해 줌
        
# 데이터 구조 및 자료형 분석
## 자료형 변환
- 문제: int 자료형이어야 하는데 float 자료형인 컬럼이 있다.
- 새롭게 알게 된 점:
    - 결측치 때문에 정수가 실수형으로 저장될 수 있다.
    - Pandas에는 결측값을 지원하는 nullable 정수형인 `Int64`가 있음.
    -   | 자료형 | 결측값 지원 |
        | --- | --- |
        | `int64` | 일반적인 `NaN` 지원하지 않음 |
        | `float64` | `NaN` 지원 |
        | `Int64` | `pd.NA` 지원 |

