# PyTorch 딥러닝 모델 훈련을 위한 데이터 준비하기

1. 데이터를 다운로드한다.
2. 데이터의 종류(이미지/텍스트/음성 등), 크기(개수), 형태(e.g. 64 * 64 * 3), 클래스 개수 및 이름 등을 확인한다.
3. 데이터를 PyTorch Dataset (torch.utils.data.Dataset)으로 변환한다.
    - 데이터에 transform 적용 (torchvision.transforms.Compose 사용)
    - 데이터를 Tensor로 변환함
    - train_data, test_data를 각각 따로 만듦
    - ImageFolder 등 PyTorch에서 제공하는 함수를 사용하거나, torch.utils.data.Dataset을 상송해서 커스텀 Dataset 클래스 만들기 (__getitem__ 메서드 정의 필수!)
4. Dataset을 PyTorch DataLoader (torch.utils.data.DataLoader)로 변환한다.
    - 데이터를 batch 단위로 묶고 iterable하게 만들어줌. (데이터를 한 batch씩 뽑아와서 학습할 수 있게 해줌)
    - dataset, batch_size, num_workers, shuffle 설정 필요
    - num_workers = os.cpu_count() 추천