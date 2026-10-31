새로운 Python 개념과 활용 방법

# `Path` 클래스
- 문제: CSV 파일을 절대경로로 지정해서 관리하고 있었음
- 새롭게 알게 된 점: `Path` 객체는 경로를 조합하고, 파일 존재 여부 및 확장자 등을 확인하는 기능을 제공함.
- 활용 방법:
    - `rental_log_path = Path("../data/raw/bike_rental_log_2601.csv")`
    - `rental_log_path.exists()`
