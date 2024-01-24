# Ordered GNN![](pics/nested_tree.png#id=MTGKF&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=&width=400) 

## 需要安装的依赖包

```
python==3.8.12
torch==1.11.0
torch_geometric==2.0.4
torch_sparse==0.6.13
torch_scatter==2.0.9
torch_cluster==1.6.0
torch_spline_conv==1.2.1
wandb==0.12.16
```

## Run

代码使用wandb进行管理，下面是你需要做的操作：

-  安装环境之后，需要修改下面的环境变量
```bash
export WANDB_entity=$YOUR_WANDB_ENTITY$
export WANDB_project=$YOUR_WANDB_PROJECT$
```
 

- 选择对应的的文件就可以进行对应的实验
```bash
python sweep.py --sweep_file=best_params/over-smoothing_Cora_OrderedGNN_4.yaml
```
 

- 你将会得到这个两个数据 `$SWEEP_ID$` 和 `$SWEEP_URL$`
```bash
Create sweep with ID: $SWEEP_ID$
Sweep URL: $SWEEP_URL$
```

接着把变量加入下面这个命令中
```bash
python agents.py --sweep_id=$SWEEP_ID$ --gpu_allocate=$INDEX_GPU$:$PARALLEL_RUNS$
```

## 
