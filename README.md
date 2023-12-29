# Sequential-Model

전처리
1. csv_files 파일의 csv 데이터들을 하나로 합치고 rotation x, y, z만 사용
2. 모든 값을 -180 ~ 180 사이로 정규화
3. 직전 프레임과 rotation 변화량을 비교해서 3단계 (느림, 중간, 빠름) 으로 구분
4. combined_df.csv 저장

Model
1. train, test로 나눔
2. LSTM (Transformer) 모델 지정
3. 머리, 왼손목, 오른손목 rotation x, y, z(9개) 데이터에 weight 2 적용
4. rotation 변화량 3단계에 따라서 1, 1.5, 2 weight 적용
5. compile 후 train
