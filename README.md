# LFME

Official implementation for "[LFME: A Simple Framework for Learning from Multiple Experts in Domain Generalization](https://arxiv.org/abs/2410.17020)" in NeurIPS 2024.

# The Free Lunch for Generalization

Simple combination of two baselines (i.e. CE and MSE losses)

```
logits = self.predict(all_x)
loss_ce = F.cross_entropy(logits, all_y)
all_y_one_hot = F.one_hot(all_y, num_classes=logits.shape[1]).float()
loss_mse = F.mse_loss(logits, all_y_one_hot)

#alpha can be value, personally recommend it within the range of [0.01, 10]
loss = loss_ce + alpha*loss_mse 
```


# Citation
If you find this work useful, please consider citing it.

```
@inproceedings{chen2024lfme,
  title={LFME: A Simple Framework for Learning from Multiple Experts in Domain Generalization},
  author={Chen, Liang and Zhang, Yong and Song, Yibing and Shen, Zhiqiang and Liu, Lingqiao},
  booktitle={NeurIPS},
  year={2024}
}

```

Please contact me via email (liangchen527@gmail.com) if your have any questions regarding this project.
