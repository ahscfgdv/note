# linux

## 文件操作

### cp命令

`cp` 命令是 Linux 中用于复制文件和目录的命令。它能够将文件或目录从一个位置复制到另一个位置。以下是一些常用的 `cp` 命令参数及其解释：

```bash
cp [options] source destination
```

- `source`：要复制的源文件或目录。
- `destination`：目标位置或目录。

1. **-r, --recursive**
    - 递归地复制目录及其内容。

2. **-i, --interactive**
    - 交互式操作，如果目标文件已存在，会提示是否覆盖。

3. **-u, --update**
    - 仅在源文件比目标文件新或目标文件不存在时才进行复制。

4. **-v, --verbose**
    - 显示详细的复制信息。

5. **-a, --archive**
    - 归档模式，保留文件所有者、权限等元数据，并进行递归复制。

6. **-b, --backup**
    - 创建备份文件。

7. **-f, --force**
    - 强制复制，覆盖目标位置已存在的文件。

8. **-n, --no-clobber**
    - 不覆盖目标位置已存在的文件。

9. **-p, --preserve**
    - 保留源文件的权限、时间戳等信息。

10. **--help**
    - 显示命令的帮助信息。

11. **--version**
    - 显示命令的版本信息。

12. **复制文件到目录**：

    ```bash
    cp file1 file2 directory/
    ```

    这将 `file1` 和 `file2` 复制到 `directory` 目录下。

13. **递归复制目录及其内容**：

    ```bash
    cp -r source_directory/ destination_directory/
    ```

    将 `source_directory` 及其内容复制到 `destination_directory`。

14. **交互式复制**：

    ```bash
    cp -i file1 file2 directory/
    ```

    如果目标位置已有同名文件，会提示是否覆盖。

15. **保留文件元数据**：

    ```bash
    cp -a source_directory/ destination_directory/
    ```

    这会归档模式地复制，保留所有者、权限等元数据。

参数的组合可以根据具体的需求进行调整。记住，当你使用 `cp` 命令时，要确保你有权限在目标位置进行复制。

### mv命令

`mv` 命令是 Linux 中用于移动文件或重命名文件的常用命令，它有一些常用的参数，下面是这些参数的详细解释：

```bash
mv [options] source destination
```

- `source`：要移动或重命名的文件或目录。
- `destination`：目标位置或新的文件名。

1. **-f, --force**
    - 强制执行移动操作，覆盖目标位置已存在的文件。

2. **-i, --interactive**
    - 交互式操作，移动文件时会询问是否覆盖已存在的文件。

3. **-n, --no-clobber**
    - 不覆盖已存在的文件，如果目标位置有同名文件存在，不执行移动操作。

4. **-u, --update**
    - 只在源文件比目标文件新或者目标文件不存在时才执行移动操作。

5. **-v, --verbose**
    - 显示详细的移动过程，列出每个移动的文件。

6. **-b, --backup**
    - 在移动目标文件之前，先创建备份。

7. **-S, --suffix**
    - 与 `-b` 一起使用，指定备份文件的后缀名。

8. **-t, --target-directory=目录**
    - 将源文件移动到指定目录，而不是将目录移动到目标位置。

9. **-T, --no-target-directory**
    - 强制将多个源文件移动到单个目录而不创建子目录。

10. **--help**
    - 显示命令的帮助信息。

11. **--version**
    - 显示命令的版本信息。

这些参数可以单独使用，也可以组合使用，根据你的需求进行选择。例如，`mv -i file1 file2 directory/` 将交互式地移动 `file1` 和 `file2` 到 `directory` 目录下，询问是否覆盖同名文件。

### tar

`tar` 命令用于创建和提取归档文件（通常称为 tarball），它将多个文件合并到一个文件中，然后可以压缩这个文件以节省空间。下面是 `tar` 命令的一些常用参数及其解释：

### 创建归档文件

1. **-c, --create**
    - 创建归档文件。

2. **-f, --file=文件名**
    - 指定归档文件的名称。

3. **-v, --verbose**
    - 显示详细的操作过程。

4. **-z, --gzip**
    - 使用 gzip 压缩归档文件。

5. **-j, --bzip2**
    - 使用 bzip2 压缩归档文件。

6. **-C, --directory=目录**
    - 在指定的目录中执行操作。

7. **-p, --preserve-permissions**
    - 保留文件权限信息。

8. **-x, --extract, --get**
    - 提取归档文件。

9. **-t, --list**
    - 列出归档文件中的内容。

10. **--strip-components=数值**
    - 提取时去除路径前的指定层数。

11. **-r, --append**
    - 向归档文件中追加文件。

12. **-u, --update**
    - 仅添加比归档文件中已有同名文件更新的文件。

13. **-d, --diff, --compare**
    - 比较归档文件与文件系统中的文件差异。

14. **--delete**
    - 从归档文件中删除指定的文件。

15. **--exclude=模式**
    - 排除符合模式的文件或目录。

16. **--help**
    - 显示命令的帮助信息。

17. **--version**
    - 显示命令的版本信息。

`tar` 命令的参数组合和具体用法会根据你的需求和场景有所不同。例如，要创建一个压缩的归档文件，可以使用 `tar -czvf archive.tar.gz files/`，其中 `-c` 表示创建，`-z` 表示使用 gzip 压缩，`-v` 表示显示详细信息，`-f` 指定归档文件名称，`files/` 是要归档的文件目录。

### 配置ssh服务

**安装ssh server**
`sudo apt install openssh-server`
**配置免密登录**

```bash
cd ~/.ssh/    # 若没有该目录,先执行ssh localhost
ssh-keygen -t rsa    # 出现提示,全部回车即可
cat ./id_rsa.pub >> ./authorized_keys
```

### ubuntu配置下载源

<https://blog.csdn.net/weixin_53000184/article/details/130782900>
