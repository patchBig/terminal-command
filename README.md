# terminal

## 批量删除 git 分支

- `git branch` 输出当前分支列表
- `grep` 是对 `git branch` 的输出结果进行匹配，匹配值当然就是 `branchName`
- `xargs` 的作用是将参数列表转换成小块分段传递给其他命令

```bash
# 从分支列表中匹配到指定分支，然后一个一个(分成小块)传递给删除分支的命令，最后进行删除。
git branch |grep 'branchName' |xargs git branch -D
```

这是通过 shell 管道命令来实现的批量删除分支的功能
