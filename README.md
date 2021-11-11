# tensorboard_summary

## tensorboard에 값 추가 하는법

- import tensorboard

```
from tensorboardX import SummaryWriter
```

- summary init
  > 저장할 폴더

```
summary = SummaryWriter(os.path.join("./runs", args.exp_name))
```

- scalar 값 추가
  > 저장할 변수 이름, 저장할 변수(값), iteration 혹은 epoch 의 순서

```
ex>
summary.add_scalar('Loss/Valid Loss', valid_loss, (epoch + 1))
```

- image 추가
  > 저장할 변수 이름, 저장할 변수(값), iteration 혹은 epoch의 순서, 이미지 데이터 포맷 의 순서

```
ex>
writer.add_image("val/gt_rgb", target, global_step=i, dataformats='HWC')
```

## tensorboard 접속법

- 로컬에서
  > 뒤에 6006 포트(기본 포트)를 \*\* 두개 사이에 있는 포트로 포트 포워딩 한다는 의미(6006 -> 16006)

```
ssh -L **16006**:127.0.0.1:6006 dogyoon@165.132.125.83 -p 22
```

- 켜진 창에서
  > --logdir은 summary init 한 폴더, 포트는 포워딩 한 포트

```
tensorboard --logdir=./runs/dgcnn_1024 --port=6006
```

- 웹에서 로컬창에서 접속

```
127.0.0.1:**16006**
```

## 종료

- summary 종료

```
summary.close()
```
