# tensorboard_summary

## add scalar 하는법

- import tensorboard

```
from tensorboardX import SummaryWriter
```

- summary init

```
summary = SummaryWriter(os.path.join("./runs", args.exp_name))
```

```
summary.add_scalar('Loss/Valid Loss', valid_loss, (epoch + 1))
```

## tensorboard 접속법

- 로컬에서

```
ssh -L **16006**:127.0.0.1:6006 dogyoon@165.132.125.83 -p 22
```

- 켜진 창에서

```
tensorboard --logdir=./runs/dgcnn_1024 --port=6006
```

```
127.0.0.1:**16006**
```

- 으로 로컬창에서 접속

## 종료

- summary 종료

```
summary.close()
```
