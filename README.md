[TOC]



# 基本命令的使用

1. **大小写敏感：** Linux 是大小写敏感的，所以 `Hello` 和 `hello` 是两个不同的文件或命令。

2. **文件系统：** Linux 将文件和目录组织成一个树形结构，类似于 Windows 的文件系统。根目录（/）位于文件系统的顶部。

3. **命令格式：** 一般来说，Linux 命令的格式为 `command options arguments`。其中，命令是你要执行的操作，选项是命令的标志，用来改变命令的行为，而参数是命令操作的对象。

4. **通配符：** 在 Linux 中，通配符用于匹配文件名。常见的通配符包括 `*`（匹配零个或多个字符）、`?`（匹配任意单个字符）和`[]`（匹配括号内的任何字符）。

5. **权限：** Linux 使用权限来控制文件和目录的访问。每个文件和目录都有一个所有者和一个所属组，以及针对所有者、所属组和其他用户的权限设置。

6. **管道和重定向：** Linux 允许你使用管道（`|`）将一个命令的输出发送到另一个命令，并使用重定向符号（`>` 和 `<`）来改变命令的输入和输出。

   1. 管道（Pipeline）是 Linux 中非常强大和常用的概念，它允许将一个命令的输出作为另一个命令的输入，以此来串联多个命令，实现复杂的数据处理和操作。在命令行中，管道由竖线符号 `|` 表示。

      ​	下面是管道的一些重要特点和使用方式：

      1. **命令串联：** 管道允许将多个命令连接起来，使得每个命令的输出成为下一个命令的输入。例如：

         ```
         command1 | command2 | command3
         ```

         这里 `command1` 的输出将作为 `command2` 的输入，而 `command2` 的输出又将作为 `command3` 的输入。

      2. **实时处理：** 管道允许实时处理数据流，即在数据生成的同时就开始处理，而不需要等待所有数据都生成完毕。这对于处理大型数据或持续产生的数据流非常有用。

      3. **灵活性：** 你可以根据需要串联任意数量的命令，从而实现复杂的数据处理和操作。这使得管道成为了构建自定义数据处理流程的强大工具。

      4. **示例应用：** 管道常用于文本处理，如过滤、排序、统计等。例如，你可以使用 `grep` 命令来过滤文本中的特定行，然后使用 `sort` 命令来对其进行排序，最后使用 `uniq` 命令来去除重复行：

         ```
         grep "pattern" file.txt | sort | uniq
         ```

      5. **错误处理：** 默认情况下，只有命令的标准输出被重定向到管道，而标准错误输出仍然会在终端显示。如果需要将标准错误输出也重定向到管道中，可以使用 `2>&1` 语法。例如：

         ```
         command1 2>&1 | command2
         ```

         这样，`command1` 的标准输出和标准错误输出都会作为 `command2` 的输入。

      6. **效率考虑：** 尽管管道非常灵活，但过多的管道可能会导致性能下降。因此，在设计管道时，需要权衡灵活性和性能之间的关系，尽量保持管道简洁高效。

         总之，管道是 Linux 命令行中非常重要的概念，能够极大地提高命令行的灵活性和功能性，同时也需要谨慎使用，以免影响系统性能。

7. **环境变量：** Linux 中的环境变量是一种全局变量，用于存储系统配置和用户偏好设置。你可以使用 `export` 命令设置和管理环境变量。

8. **帮助：** Linux 提供了广泛的文档和帮助资源，你可以使用 `man` 命令查看命令的手册页，或者使用 `--help` 选项来获取命令的简要帮助信息。

9. **文件和目录操作：** 了解如何在 Linux 中创建、复制、移动、重命名和删除文件和目录是至关重要的。常用的命令包括 `mkdir`（创建目录）、`cp`（复制文件）、`mv`（移动文件或重命名文件）、`rm`（删除文件）等。

10. **文件内容查看和编辑：** 你可能需要查看文件的内容或者编辑文件。常用的命令包括 `cat`（显示文件内容）、`less`（逐页查看文件内容）、`nano`（简单的文本编辑器）等。

# 安装git

> 要在Ubuntu上安装Git，你可以通过终端执行以下命令：
>
> ```
> sudo apt update
> sudo apt install git
> ```
>
> 第一条命令会更新你的软件包列表，确保你获取到最新的可用软件包。第二条命令则是用来安装Git。安装完成后，你就可以在终端中使用Git了。

它回复sudo:apt:command not found

> 哦，看来你的系统中可能没有apt命令。在某些Ubuntu的衍生版本中，可能会使用不同的软件包管理器。你可以尝试使用以下命令来安装Git：
>
> ```
> sudo apt-get update
> sudo apt-get install git
> ```
>
> 这个命令跟之前的类似，只是用了apt-get而不是apt。这个命令也会更新软件包列表并安装Git。

# 查看ip地址

> 要在Linux系统上查看IP地址，你可以使用`ifconfig`命令或`ip`命令。
>
> 1. 使用 `ifconfig` 命令：
>
> ```
> ifconfig
> ```
>
> 这将显示你的网络接口信息，包括IP地址、子网掩码、网关等。
>
> 2. 使用 `ip` 命令：
>
> ```
> ip addr show
> ```
>
> 或者只输入 `ip addr` 也可以。
>
> 这将显示类似的网络接口信息，包括IP地址、子网掩码、网关等。`ip`命令是新一些的工具，用于网络配置和管理，它提供了更多的功能和选项。
>
> 无论使用哪种方法，你都应该能够在输出中找到你的IP地址信息。

# 重启

> 要在Linux系统上重启，你可以使用 `reboot` 命令。在终端中输入以下命令并按下回车：
>
> ```
> sudo reboot
> ```
>
> 这将提示你输入管理员密码（如果当前用户有权限），然后系统将开始重启。

# pip命令找不到

> 这个错误提示意味着你的系统中没有找到 `pip` 命令。`pip` 是 Python 的包管理器，用于安装 Python 包。错误提示建议你通过以下命令安装 `pip`：
>
> ```
> sudo apt install python3-pip
> ```
>
> 这将使用 apt 包管理器安装 Python 3 版本的 `pip`。输入密码后，系统会开始安装 `pip`。完成后，你就可以再次尝试运行 `pip install -r requirement.txt` 命令了。

# ssh

**登录**

> [用户名]@[ip地址]

**退出**

> exit

# 本地与远程机器传输文件(拷贝)

## 从本地到远端

**目录**

`scp -r [本地文件地址] [远程计算机用户名]@[ip]：(~/a/b/c)[远程目录]`

`rsync -r source_dir username@ip_address:/home/username/target_dir`

**文件**

`scp filename username@ip_address:/home/username`

`rsync filename username@ip_address:/home/username`

## 从远端到本地

**文件**

`scp username@ip_address:/home/username/filename 本地目录`

`rsync username@ip_address:/home/username/filename 本地目录`

**目录**

[同上](**目录**)

# 查看文件

> 在Ubuntu中，你可以使用`ls`命令来查看指定目录下的文件。要查看特定目录中的文件，只需在`ls`命令后面提供目录的路径即可。
>
> 例如，如果要查看当前目录下的文件，只需在终端中输入：
>
> ```
> ls
> ```
>
> 如果要查看指定目录（比如`/home/user/documents`）下的文件，可以输入：
>
> ```
> ls /home/user/documents
> ```
>
> 这将显示`/home/user/documents`目录中的所有文件和子目录的列表。

# 查看任务进程

在Linux中，你可以使用一些命令来查看当前正在运行的任务。其中最常用的是`top`命令。`top`命令可以显示系统中正在运行的进程以及相关的信息，例如进程ID、CPU使用率、内存使用情况等等。只需在终端中输入`top`并按下回车键即可查看。

另外，你也可以使用`ps`命令来查看进程信息。例如，`ps aux`命令可以列出当前系统中所有进程的详细信息。这些信息包括进程ID（PID）、CPU使用率、内存使用情况等等。

如果你想查看特定用户的进程，可以使用`ps -u username`命令，将`username`替换为你要查看的用户名。

最后，如果你只想查看自己的进程，可以使用`ps aux | grep <your_username>`命令，将`<your_username>`替换为你的用户名。

# 使用top查看CPU状态

<img src="https://cdn.jsdelivr.net/gh/xff133/wodetuhchuang@main/image-20240713131750912.png" alt="image-20240713131750912" style="zoom:50%;" />

​	•	us：用户态的CPU使用率

​	•	sy：系统态的CPU使用率

​	•	ni：低优先级进程的CPU使用率

​	•	id：空闲CPU的百分比

​	•	wa：IO等待的CPU百分比

​	•	hi：硬中断的CPU百分比

​	•	si：软中断的CPU百分比

​	•	st：被偷取的CPU百分比（虚拟机中用）解压缩文件

基本上`us+sy+ni`就是总的CPU占用率了，也可以总100%的减去空闲的`id`

# 解压缩

要在Ubuntu中将文件解压到指定目录，你可以使用`unzip`命令来解压`.zip`文件，或者使用`tar`命令来解压`.tar.gz`或`.tar.bz2`等压缩文件。以下是一些示例：

1. **解压`.zip`文件到指定目录**：

```bash
unzip file.zip -d /path/to/destination
```

这将把`file.zip`解压到`/path/to/destination`目录中。

2. **解压`.tar.gz`文件到指定目录**：

```bash
tar -xzf file.tar.gz -C /path/to/destination # C是大写
```

这将把`file.tar.gz`解压到`/path/to/destination`目录中。

```bash
tar -xzvf vim.tar.gz
```

`x`: 表示解压文件。

`z`: 表示解压的是一个 `.gz` 文件。

`v`: 表示显示详细信息。

`f`: 表示操作的文件名。

如果你需要更详细的进度输出，可以用 `--checkpoint` 参数。例如：

```bash
tar --checkpoint=100 -xzf vim.tar.gz
```

解释：

- `--checkpoint=100`: 每解压 100 个文件会输出一条进度信息。

这对于解压包含大量文件的压缩包非常有用。

也可以通过配合其他工具（如 `pv` 或 `progress`）显示更加直观的进度条。以下是使用 `pv` 的方法：

1. 确保安装 `pv` 工具（若未安装，可以通过 `apt install pv` 安装）。

2. 使用如下命令：

   ```
   pv vim.tar.gz | tar -xzvf -
   ```

   - `pv`: 会显示解压过程中的数据流量。
   - `|`: 管道符，将数据传递给 `tar`。

运行后，你会看到一个实时更新的进度条。

3. **解压`.tar.bz2`文件到指定目录**：

```bash
tar -xjf file.tar.bz2 -C /path/to/destination
```

这将把`file.tar.bz2`解压到`/path/to/destination`目录中。

确保替换命令中的`file.zip`、`file.tar.gz`或`file.tar.bz2`以及`/path/to/destination`为你实际的文件和目录路径。

**注意C是大写**

## .gz

在Linux中，要解压.gz文件，你可以使用`gzip`命令。下面是解压缩.gz文件的基本语法：

```
gzip -d filename.gz
```

这将会将`filename.gz`解压缩为`filename`，并将原始的.gz文件删除。如果你不想删除原始的.gz文件，你可以使用`-k`选项：

```
gzip -dk filename.gz
```

这样会在解压缩后保留原始的.gz文件。

另外，你也可以使用`gunzip`命令，它其实是`gzip -d`的别名，效果相同：

```
gunzip filename.gz
```

以上是最基本的用法。如果你想了解更多选项，你可以查看`gzip`和`gunzip`命令的帮助文档：

```
man gzip
man gunzip
```

## 压缩文件

在Linux中，你可以使用几种不同的命令来压缩文件。以下是一些常用的压缩命令：

1. **使用`tar`命令**：
   - 创建一个`.tar`文件：
     ```bash
     tar -cvf archive.tar /path/to/directory
     ```
   - 创建一个压缩的`.tar.gz`文件：
     ```bash
     tar -czvf archive.tar.gz /path/to/directory
     ```

2. **使用`gzip`命令**：
   
   - 压缩单个文件：
     ```bash
     gzip filename
     ```
   
3. **使用`zip`命令**：
   - 压缩文件或目录：
     ```bash
     zip -r archive.zip /path/to/directory
     ```

你可以根据需要选择适合的命令和选项。

# 软件运行缺少依赖的库

(base) xiaoluxi@xiaoluxi:~/clash$ ./cfw ./cfw: error while loading shared libraries: libatk-1.0.so.0: cannot open shared object file: No such file or directory 这是什么意思？

> 这个错误意味着在尝试运行 `./cfw` 时，系统无法找到名为 "libatk-1.0.so.0" 的共享库文件。共享库是一组可被多个程序共享的函数和资源，通常由许多程序使用，而不是每个程序都包含一份。这些库通常由操作系统或者其他软件提供。
>
> 在你的情况下，程序 `cfw` 需要依赖于 `libatk-1.0.so.0` 这个共享库，但系统找不到这个文件。这可能是由于以下原因之一引起的：
>
> 1. **缺少依赖项**：你的系统缺少了所需的共享库文件。你需要安装 `libatk` 库来解决这个问题。你可以通过包管理工具来安装它，具体命令可能因你的操作系统而异。例如，在基于 Debian 的系统中，你可以使用以下命令安装：
>
>    ```
>    sudo apt-get install libatk1.0-dev
>    ```
>
>    在其他发行版的 Linux 中，可能需要使用不同的命令。
>
> 2. **库文件路径问题**：如果 `libatk-1.0.so.0` 存在于系统中，但程序无法找到它，可能是因为库文件路径不在默认搜索路径中。你可以将库文件的路径添加到 `LD_LIBRARY_PATH` 环境变量中，或者将库文件放置在系统默认的库文件路径下。
>
> 3. **库文件损坏**：如果库文件损坏了或不完整，也会导致这个错误。你可能需要重新安装或修复 `libatk` 库。
>
> 解决这个问题的具体方法取决于你的操作系统和系统配置。

(base) xiaoluxi@xiaoluxi:~$ ./clash/cfw ./clash/cfw: error while loading shared libraries: libatk-bridge-2.0.so.0: cannot open shared object file: No such file or directory 那这个又是什么意思？

> 这个错误与之前的类似，只是这次程序 `cfw` 需要依赖于另一个共享库 `libatk-bridge-2.0.so.0`，但系统同样找不到这个文件。解决方法与之前类似：
>
> 1. **缺少依赖项**：你需要安装 `libatk` 的桥接库来解决这个问题。具体命令可能因你的操作系统而异，但通常你可以使用包管理工具来安装。
>
> 2. **库文件路径问题**：检查库文件的路径是否正确，如果存在于系统中但程序无法找到，可以尝试添加路径到 `LD_LIBRARY_PATH` 环境变量中，或者将库文件放置在系统默认的库文件路径下。
>
> 3. **库文件损坏**：如果库文件损坏了或不完整，也会导致这个错误。你可能需要重新安装或修复 `libatk` 库。
>
> 在解决这个问题时，可以参考之前提到的建议，并根据你的操作系统和系统配置来执行相应的操作。

# conda

**删除环境**

`conda remove --name 你的虚拟环境名称 --all`

**查看创建了哪些环境**

`conda env list`

**查看环境的位置**

`conda info --envs`

## conda换源

### 添加源

如果使用 `conda create -n wcra` 命令时速度很慢，可以尝试以下几种方法加速：

#### 1. 更换镜像源

使用国内镜像源可以显著提高下载速度。以下是一些常用的镜像源：

- 清华大学

```bash
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```

- 中科大

```bash
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```

> 最好只保留更换的镜像源，不要其他的，不然还是很慢

#### 2. 使用 mamba

`mamba` 是一个更快的包管理器，兼容 `conda`。安装 `mamba` 后，可以用它来创建环境和安装包：

```bash
conda install mamba -n base -c conda-forge
mamba create -n wcra
```

#### 3. 离线安装

如果你有其他机器上已经安装好的环境，可以使用 `conda-pack` 打包，然后在目标机器上解压。

#### 4. 更新 conda

确保你使用的是最新版本的 `conda`，可以使用以下命令更新：

```bash
conda update conda
```

尝试这些方法，应该能改善速度问题。

### 临时换源

如果你只想临时更换 `conda` 的源，可以在创建环境时指定 `-c` 选项来使用特定的镜像。比如：

#### 清华大学镜像

```bash
conda create -n wcra -c https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/ package_name
```

#### 中科大镜像

```bash
conda create -n wcra -c https://mirrors.ustc.edu.cn/anaconda/pkgs/main/ package_name
```

在这里，`package_name` 是你要安装的具体包的名称。如果不想指定包，可以先创建环境，然后再安装包：

```bash
conda create -n wcra python
conda install -c https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/ package_name
```

这样，你可以在完成安装后恢复到默认源。

#### 创建环境临时换源

如果创建环境时速度太慢，临时更换源可以使用 `--override-channels` 选项，直接在命令中指定要使用的源，而忽略默认源。这样可以加快环境创建的速度。

例如，使用清华大学的镜像：

```bash
conda create -n wcra --override-channels -c https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/ -c https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/ python
```

这样创建环境时就会使用指定的源，应该会更快。
## 环境迁移-`conda pack`
`conda-pack` 是一个工具，用于将完整的 Conda 环境打包成一个独立的压缩文件（如 `.tar.gz`），便于在其他机器上解压并直接使用，而无需重新安装依赖。以下是使用 `conda-pack` 的详细步骤：

---

### 1. **安装 `conda-pack`**
如果尚未安装 `conda-pack`，可以使用 `conda` 或 `pip` 安装：

```bash
conda install -c conda-forge conda-pack
```

或者用 `pip`：

```bash
pip install conda-pack
```

---

### 2. **打包 Conda 环境**
运行以下命令，将 Conda 环境打包为一个 `.tar.gz` 文件：

```bash
conda pack -n <environment_name> -o <output_file.tar.gz>
```

#### 示例：
```bash
conda pack -n my_env -o my_env.tar.gz
```

- `-n <environment_name>`：指定要打包的环境名称。
- `-o <output_file.tar.gz>`：指定输出的压缩包文件名。

---

### 3. **将压缩包复制到目标机器**
可以使用 `scp` 或其他工具将 `.tar.gz` 文件复制到目标机器：

```bash
scp my_env.tar.gz user@remote_host:/path/to/destination
```

---

### 4. **在目标机器上解压环境**
在目标机器上解压 `.tar.gz` 文件：

```bash
mkdir -p <target_directory>
tar -xzf my_env.tar.gz -C <target_directory>
```

#### 示例：
```bash
mkdir -p ~/my_env
tar -xzf my_env.tar.gz -C ~/my_env
```



解压后，您的环境会存放在 `<target_directory>` 中。

**\- 推荐步骤**
> 直接进入到环境目录，以我的为例：  
我的环境在`~/miniconda3/envs/`中，直接在这里创建一个环境名的文件夹，比如`~/miniconda3/envs/new_env`，然后在这下面解压文件`my_env.tar.gz`,这就就直接得到了环境`new_env`  
你就可以直接使用 **`conda activate new_env`** 来激活环境
---

### 5. **修复路径（可选）**
如果原始环境的路径和目标机器的路径不同，可能需要修复路径。`conda-pack` 提供了便捷的路径修复方法：

进入解压后的目录：

```bash
cd <target_directory>/my_env
```

运行以下命令修复路径：

```bash
./bin/conda-unpack
```

这将修复环境中的所有硬编码路径。

---

### 6. **激活环境**
在目标机器上，可以直接使用该解压后的环境，而无需安装 `conda` 或重新创建环境。

激活解压环境的方法是通过直接调用 `bin/python` 或运行脚本：

```bash
<target_directory>/my_env/bin/python
```

如果需要运行脚本或激活环境：
```bash
source <target_directory>/my_env/bin/activate
```

---

### 7. **清理临时文件**
在解压和修复路径完成后，您可以选择删除压缩包以节省空间：

```bash
rm my_env.tar.gz
```

---

### 优势与使用场景

- **快速迁移环境**：适用于需要在其他机器上直接使用同样的环境，而无法安装 Conda 的场景。
- **独立环境**：打包的环境与原 Conda 环境隔离，可直接运行，不依赖 Conda 本身。
- **无网络场景**：在没有网络连接的服务器上非常有用。

通过以上步骤，您可以轻松使用 `conda-pack` 将环境打包并迁移到其他机器上！

# 能ping通但不能ssh连接

**可能是ubuntu没有开启ssh服务**

输入`sudo service sshd restart`开启

# 运行AppImage文件

一般可以直接双击运行

或者给它**设置权限**

# 百度网盘(Linux)

**安装**

```
pip install bypy
```

**授权**

```
bypy info
```

进入它给你提供的网页进行授权即可

**命令**

- `help <command>` - 为命令提供一些信息
- `cdl_add <source_url> [save_path] [timeout]` - 添加离线（云）下载任务
- `cdl_addmon <source_url> [save_path] [timeout]` - 添加离线（云）下载任务并监控下载进度
- `cdl_cancel <task_id>` - 取消离线（云）下载任务
- `cdl_list` - 列出离线（云）下载任务
- `cdl_query <task_ids>` - 查询现有离线（云）下载任务
- `cleancache` - 删除哈希缓存文件中的无效条目
- `combine <remotefile> [localfile] [md5s]` - 尝试在 PCS 上通过组合指定 MD5 的片段来创建文件
- `compare [remotedir] [localdir]` - 比较远程目录和本地目录
- `copy/cp <from> <to>` - 在百度云远程复制文件/目录
- `delete/remove/rm <remotepath>` - 在百度云远程删除文件/目录
- `downdir [remotedir] [localdir]` - 下载远程目录（递归下载）
- `downfile <remotefile> [localpath]` - 下载一个远程文件。
- `download [remotepath] [localpath]` - 下载远程目录（递归）/文件
- `dumpcache` - 显示文件哈希缓存
- `list/ls [remotepath] [format] [sort] [order]` - 列出百度 PCS 中的 "remotepath "目录
- `listrecycle [start] [limit]` - 列出回收内容
- `meta <remotepath> [format]` - 在百度云中获取给定路径（目录/文件）的信息。
- `mkdir <remotedir>` - 在百度云创建目录
- `move/mv/rename/ren <from> <to>` - 在百度云远程移动文件/目录
- `quota/info` - 显示配额信息
- `refreshtoken` - 刷新访问令牌
- `restore <remotepath>` - 从回收站恢复文件
- `search <keyword> [remotepath] [recursive]` - 在百度云使用关键字搜索文件
- `stream <remotefile> <localpipe> [format] [chunk]` - 将云端转换为 M3U 格式的视频/音频文件流式传输到管道。
- `syncdown [remotedir] [localdir] [deletelocal]` - 从远程目录同步到本地目录
- `syncup [localdir] [remotedir] [deleteremote]` - 从本地目录同步到远程目录
- `upload [localpath] [remotepath] [ondup]` - 上传文件或目录（递归方式）
- `whoami` - 显示用户信息

# 关于网络代理的问题

**\-描述**

> 在克隆仓库的时候，提示`fatal: 无法访问 'https://github.com/ChenHongruixuan/MambaCD.git/'：Failed to connect to 127.0.0.1 port 7890 after 0 ms: 连接被拒绝`
>
> 这是因为网络启用了代理，端口是7890。这还可能会影响到ssh连接的稳定性。解决办法是把网络代理关了即可

用以下命令取消代理

```bash
unset http_proxy
unset https_proxy
```

可用`curl`命令来测试一下

```bash
curl -I <url>
```

设置系统代理

1. http和https
   ```bash
   export http_proxy="http://127.0.0.1:7890"
   export https_proxy="http://127.0.0.1:7890"
   ```

2. socks
   ```bash
   export all_proxy="socks5://127.0.0.1:7891"
   ```

   

# 怎么测试网速

在Linux系统中测试网速，您可以使用多种命令行工具。以下是一些常用的方法：
1. **speedtest-cli**：
   `speedtest-cli` 是一个用Python编写的命令行工具，用于测试互联网连接速度。它使用Speedtest.net的服务器进行测试。
   - 首先，您需要安装 `speedtest-cli`。在大多数Linux发行版中，您可以使用pip来安装：
     ```bash
     sudo apt-get install python-pip
     pip install speedtest-cli
     ```
   - 安装完成后，您可以通过以下命令来测试您的网速：
     ```bash
     speedtest-cli
     ```
2. **curl**：
   `curl` 是一个用于数据传输的命令行工具，也可以用来测试网速，尽管它不如 `speedtest-cli` 直观。
   - 下载测试：
     ```bash
     curl -o /dev/null http://speedtest.wdc01.softlayer.com/downloads/test10.zip
     ```
   - 上传测试：
     ```bash
     curl -F "file=@/path/to/local/file" http://speedtest.wdc01.softlayer.com/upload.php
     ```
3. **wget**：
   `wget` 是一个在命令行下工作的非交互式网络下载工具，也可以用来进行简单的速度测试。
   - 使用 `wget` 测试下载速度：
     ```bash
     wget --output-document=/dev/null http://speedtest.wdc01.softlayer.com/downloads/test10.zip
     ```
4. **iperf**：
   `iperf` 是一个网络性能测试工具，可以测量TCP和UDP带宽性能。
   - 安装 `iperf`：
     ```bash
     sudo apt-get install iperf
     ```
   - 作为服务器运行 `iperf`：
     ```bash
     iperf -s
     ```
   - 在客户端运行 `iperf` 进行测试：
     ```bash
     iperf -c <server-IP>
     ```
     在使用这些工具时，请确保您有合适的权限来安装软件包，并注意遵守您所在地区的网络使用规定。在测试网速时，最好关闭其他可能占用带宽的程序，以获得更准确的测试结果。

# 查看网络占用

在Linux系统中，您可以使用多种命令行工具来查看网络占用情况。以下是一些常用的方法：
1. **nload**：
   `nload` 是一个简单易用的命令行工具，可以实时显示网络带宽的使用情况。
   - 安装 `nload`：
     ```bash
     sudo apt-get install nload
     ```
   - 运行 `nload`：
     ```bash
     nload
     ```
2. **iftop**：
   `iftop` 类似于 `top` 命令，但它用于显示实时的网络带宽使用情况。
   - 安装 `iftop`：
     ```bash
     sudo apt-get install iftop
     ```
   - 运行 `iftop`：
     ```bash
     iftop
     ```
3. **iptraf**：
   `iptraf` 是一个功能强大的网络监控工具，可以提供详细的网络统计信息。
   - 安装 `iptraf`：
     ```bash
     sudo apt-get install iptraf-ng
     ```
   - 运行 `iptraf`：
     ```bash
     iptraf
     ```
4. **vnstat**：
   `vnstat` 是一个网络流量监视器，它可以记录网络接口的流量历史数据。
   - 安装 `vnstat`：
     ```bash
     sudo apt-get install vnstat
     ```
   - 查看网络流量统计：
     ```bash
     vnstat -l
     ```
5. **tcptrack**：
   `tcptrack` 可以监视TCP连接上的数据量。
   - 安装 `tcptrack`：
     ```bash
     sudo apt-get install tcptrack
     ```
   - 运行 `tcptrack`：
     ```bash
     tcptrack -i eth0
     ```
     其中 `eth0` 应该替换为您要监视的网络接口名称。
6. **netstat**：
   `netstat` 是一个显示网络连接、路由表、接口统计信息等的工具。
   - 查看所有连接：
     ```bash
     netstat -antp
     ```
   - 查看正在监听的端口：
     ```bash
     netstat -tulnp
     ```
7. **ss**：
   `ss` 是一个工具，用于获取socket统计信息，它可以显示类似于 `netstat` 的信息，但提供更多的统计数据和更好的性能。
   - 查看所有TCP/UDP连接：
     ```bash
     ss -t -u -a
     ```
     这些工具可以帮助您监控和管理网络使用情况。在使用这些工具时，请确保您有适当的权限，并根据需要选择适合您需求的工具。

# 文本编辑

## nano

**编辑文件**

```bash
nano <文件路径>
```

**保存**

`ctrl`+`o`

保存时会让你写保存文件的名字（或者说路径）

**退出**

`ctrl`+`x`

## vim

**打开文本编辑**

`vim <path>`

**如何清空删除？**

> 在 Vim 中清空文本的方法取决于你想要清空的范围。以下是几种常见情况下的操作：
>
> 1. **清空当前行**：
>    - 在命令模式下，按下 `dd` 即可删除当前行。
>
> 2. **清空多行**：
>    - 在命令模式下，将光标移动到要清空的起始行，按下 `V` 进入可视模式。
>    - 使用方向键或其他移动光标的方式选择要清空的行数。
>    - 按下 `d` 即可删除所选行。
>
> 3. **清空整个文件**：
>    - 在命令模式下，输入 `:%d` 即可删除所有行。
>
> 4. **手动清空**：
>    - 进入编辑模式，使用删除键或者退格键清空文本内容。
>
> 选择适合你情况的方法，即可清空 Vim 中的文本内容。

**如何进行撤销操作？**

> 在 Vim 中，撤销（undo）操作非常简单。你可以使用 `u` 键来撤销之前的操作。每次按下 `u` 键，Vim 将会撤销最近的一次操作。如果你想多次撤销，则可以按下多次 `u` 键，每次按下都会撤销前一步操作。
>
> 如果你意识到撤销的太多，想要取消撤销（redo），可以使用 `Ctrl + r` 键组合。这将会重新应用之前被撤销的操作。

# 如何设置ssh免密登录

1. 客户端生成密钥对（一般情况下一路敲回车即可）
   ```
   ssh-keygen
   ```

   或者

   ```bash
   ssh-keygen -t rsa -b 4096
   ssh-keygen -t ed25519 -f ~/.ssh/custom_key_name # 这里如无必要，名称建议为 id_ed2519，如果自定义名称就需要在config里写一些配置
   ```
   
   config在`.ssh`文件夹下，如何配置其中的内容你可以参考[vscode远程连接的配置内容](# vscode远程连接)
   
   - **注意**：创建密钥的算法[`ed25519`和`RSA(4096)`](# `ed25519`和`RSA(4096)`)有所区别
   
   这俩具体有啥区别我也不知道，反正都可以用
   
   > Enter file in which to save the key (C:\Users\<username>/.ssh/id_rsa):
   
   这是问你保存文件默认的位置，一般默认即可。假如你输入`adc`那么它会保存在`C:\Users\<username>`目录下，这是不起作用，要在`C:\Users\<username>\.ssh`下才行，所以你还要把它移动到这个目录下
   
   > Enter passphrase (empty for no passphrase):
   
   这是让你设置密码，这个密码在使用**私钥**的时候会用到
   
   > Enter same passphrase again:
   
   再次输入密码以确认
   
   到此密钥生成完成，一共有两个文件：**私钥**和**公钥.pub**
   
   使用命令来查看**公钥**（这里记一下笔记，等下会考）
   
   ```
   type C:\Users\<username>\.ssh\id_rsa.pub
   ```
   
2. 服务端操作

   输入以下命令

   ```
   mkdir -p ~/.ssh
   chmod 700 ~/.ssh
   touch ~/.ssh/authorized_keys
   chmod 600 ~/.ssh/authorized_keys
   ```

   然后使用文本编辑器（如`nano`或`vim`，这里以`nano`为例）,把**公钥**（就是公钥文件中的内容）添加到`~/.ssh/authorized_keys`

   打开文件

   ```
   nano ~/.ssh/authorized_keys
   ```

   将**公钥**复制粘贴到里面即可

   然后`ctrl`+`x`保存退出
   如果是Linux或者Mac，可以使用命令行一键拷贝
   
   ```
   ssh-copy-id user@remote_server_ip
   ```

## 常见问题

1. 按照上面步骤完成了还是不能免密登录
   查看`/etc/ssh/sshd_config`文件，其中要有这两行

   ```
   PubkeyAuthentication yes
   AuthorizedKeysFile .ssh/authorized_keys
   ```

   一般都会有，主要看是不是这两行被注释掉了（就是前面加了个`#`）

# 手动执行安装脚本（网络状况不允许一键执行安装脚本的情况下）

直接在浏览器中输入地址，如`https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-release.sh`

然后把网页中的内容全选复制到执行脚本，我这里是`install-release.sh`（可以用文本编辑器打开，然后保存为`.sh`的格式就行）

然后赋予权限（`chmod +x <文件>`）

然后运行（`./install-release.sh`）

如果已经手动下载了软件，可以使用

```
./install-release.sh -l ./v2ray-linux-64.zip
```

来指定安装，就不用再等他自己下载了

# v2ray

请自行安装

**配置文件**

 `/usr/local/etc/v2ray/` 或者 `/etc/v2ray/`下一个名叫`config.json`的文件（可编辑）

**查看状态**

`sudo systemctl status v2ray`

**启动服务**

`sudo systemctl start v2ray`

**开机自动运行**

`sudo systemctl enable v2ray`

**禁止自启**

`sudo systemctl disable v2ray`

**测试**

`curl --proxy socks5h://localhost:[端口号] http://google.com`

**停止服务**

`sudo systemctl stop v2ray`

# 移动或重命令文件

在Linux系统中，你可以使用`mv`命令来移动文件。下面是使用`mv`命令的基本语法：

```
mv [option] source destination
```

其中：

- `[option]`是可选项，你可以根据需要选择是否使用。
- `source`是要移动的文件或目录的路径。
- `destination`是文件或目录的目标路径。

例如，如果你想要将文件 `file.txt` 从当前目录移动到目录 `/home/user/documents/`，你可以执行以下命令：

```
mv file.txt /home/user/documents/
```

如果你想要将文件 `file.txt` 重命名为 `newfile.txt` 并将其移动到目录 `/home/user/documents/`，你可以执行以下命令：

```
mv file.txt /home/user/documents/newfile.txt
```

注意：如果目标路径已经存在同名文件，`mv`命令将覆盖它。如果你想要避免覆盖文件，你可以使用 `-i` 选项来在移动文件之前进行确认，或者使用 `-n` 选项来避免覆盖已存在的文件。

**批量移动**

例如，如果你想要将当前目录中的所有 `.txt` 文件移动到目录 `/home/user/documents/` 中，你可以执行以下命令：

```
mv *.txt /home/user/documents/
```

这将移动所有 `.txt` 文件到指定目录。你也可以使用通配符来指定文件名模式，例如 `*.jpg` 或者 `file*.txt`。

另外，如果你想要将多个文件移动到同一个目录下，你可以在 `mv` 命令中列出所有的源文件，然后指定目标目录。例如：

```
mv file1.txt file2.txt file3.txt /home/user/documents/
```

这将把 `file1.txt`、`file2.txt` 和 `file3.txt` 移动到 `/home/user/documents/` 目录中。

总之，你可以在 `mv` 命令中指定多个源文件，并将它们移动到一个目标目录或指定的文件名中。

# 后台运行程序然后保存输出结果

要在 Linux 或 Unix 系统中后台运行程序并能随时查看其输出，你可以使用 `nohup` 命令和输出重定向结合 `tail` 命令来实现。以下是操作步骤：

1. **使用 nohup 运行你的程序**：
   ```bash
   nohup python your_script.py > output.log 2>&1 &
   ```
   这条命令会启动你的脚本并把标准输出和错误输出都重定向到 `output.log` 文件，同时 `&` 会让程序在后台运行。

   如果只运行`python your_script.py > output.log 2>&1 &`，它也会在后台运行，但是与当前终端绑定，当终端关闭时，程序也会结束运行
   
   > 在命令 `nohup python your_script.py > /path/to/your/directory/output.log 2>&1 &` 中，`1` 和 `2` 分别代表不同的输出流：
   >
   > - `1` 是标准输出（stdout），它通常用来输出程序运行的结果或数据。
   > - `2` 是标准错误（stderr），用来输出错误信息或警告。
   >
   > 这段命令中的 `2>&1` 表示将标准错误重定向到标准输出的位置，也就是说，错误和普通输出都会被记录在同一个文件 `output.log` 中。这样做可以确保你不会错过任何错误信息，它们会和其他输出一起被记录下来。
   >
   > 在命令 `nohup python your_script.py > /path/to/your/directory/output.log 2>&1 &` 的末尾，最后一个 `&` 符号是用来将命令放入后台执行。这意味着你不需要保持终端开启，命令会继续在后台运行，你可以执行其他操作或关闭终端窗口，而程序依然在后台运行。这对于长时间运行的程序或脚本非常有用，可以让你的终端不被占用。
   
2. **查看实时输出**：
   当你想要查看程序的当前输出时，可以使用 `tail` 命令查看日志文件：
   
   ```bash
   tail -f output.log
   ```
   这条命令会持续显示 `output.log` 文件的最新内容，直到你按 `Ctrl + C` 终止。

## 常见问题

1. 为什么在输入文件中还是看不到输出？
   可能是因为输出在缓存中，要过一段时间才会写入到日志文件，如果不想用缓冲，可以使用以下命令

   ```bash
   nohup python -u 1.py > log 2>&1 &
   ```

# 退出后台程序

要退出后台运行的进程，你可以使用几种方法：

1. **使用 `jobs` 命令查找后台作业**：这个命令会列出当前终端会话中所有的后台作业。
2. **使用 `fg` 命令将后台进程带到前台**：通过 `fg %jobnumber`，其中 `jobnumber` 是通过 `jobs` 命令看到的作业号码。
3. **使用 `kill` 命令终止进程**：找到进程的 PID（进程ID），可以通过 `ps` 命令查找。然后使用 `kill PID` 或 `kill %jobnumber` 来终止它。

如果你知道进程的作业号或PID，这些步骤可以帮助你有效地管理和终止后台进程。

# 制作一个系统命令

将要执行的命令写进`.sh`文件，然后把`.sh`文件移动到`/exp/home/user/.local/bin`下，然后用

```bash
sudo chomd +x 
```

赋予权限，完成之后可以在终端直接输入`xxx.sh`就可以运行，也再接着把文件名的`.sh`去掉，直接输入`xxxx`就可以运行了

## 进阶

要自定义一个Linux系统命令，你可以编写一个简单的Shell脚本。这里我将提供一个基础的示例脚本，命名为 `a`，你可以将其放置在一个适当的目录下（如 `/usr/local/bin`），并赋予执行权限。这样你就可以在任何地方通过终端运行它。

1. **创建脚本文件**：
   打开你的终端，使用文本编辑器（如 nano 或 vim）创建脚本文件：

   ```bash
   nano /usr/local/bin/a
   ```

2. **编写脚本内容**：
   在编辑器中输入以下内容：

   ```bash
   #!/bin/bash
   
   # 检查参数个数
   if [ $# -eq 0 ]; then
       echo "Usage: a [command]"
       echo "Commands:"
       echo "  help     Show this help message"
       echo "  run      Start the program"
       exit 1
   fi
   
   # 处理输入的命令
   case "$1" in
       help)
           echo "Help: This script can run a program or display help."
           ;;
       run)
           echo "Running the program..."
           # 在这里调用或执行你的程序
           ;;
       *)
           echo "Error: Unknown command '$1'"
           echo "Run 'a help' for more information."
           exit 1
           ;;
   esac
   ```

   这个脚本会检查输入的参数，并根据参数执行相应的操作。如果输入的是 `help`，它会显示帮助信息；如果是 `run`，它会执行程序。

3. **保存并退出编辑器**：
   如果你使用的是 nano，可以按 `Ctrl+X`，然后按 `Y` 键保存更改，最后按 `Enter` 键退出。

4. **给脚本文件赋予权限**：
   使脚本可执行：

   ```bash
   chmod +x /usr/.local/bin/a
   ```

5. **测试脚本**：
   现在你可以在任何地方通过命令行运行你的脚本了：

   ```bash
   a help
   a run
   ```

这就是创建和使用自定义Linux命令的基本步骤。你可以根据需要调整脚本内容，添加更多功能或修改现有功能。

**解释**

这段脚本是一个简单的bash shell脚本，用于处理命令行参数并执行相应的操作。下面我会逐行进行解释：
```bash
#!/bin/bash
```
这行表示脚本应该由bash解释器来执行。`#!/bin/bash`是一个称为shebang（或hashbang）的特殊注释，它告诉系统这个脚本应该用什么解释器来执行。
```bash
# 检查参数个数
if [ $# -eq 0 ]; then
```
这部分是注释，说明了接下来代码块的目的。`$#`代表传递给脚本的参数个数。`-eq`是bash中的比较运算符，用于判断是否相等。如果参数个数等于0，则表示用户没有提供任何参数。
```bash
    echo "Usage: a [command]"
```
`echo`命令用于输出文本到终端。这里输出的是脚本的使用方法。
```bash
    echo "Commands:"
```
这行继续输出文本，提示用户可以使用的命令。
```bash
    echo "  help     Show this help message"
```
这行输出的是`help`命令的描述，告诉用户这个命令可以用来显示帮助信息。
```bash
    echo "  run      Start the program"
```
这行输出的是`run`命令的描述，告诉用户这个命令可以用来启动程序。
```bash
    exit 1
```
`exit`命令用于退出当前shell。`1`是返回给调用脚本的父进程的退出状态码，通常表示有错误发生。
```bash
fi
```
这行表示`if`语句块的结束。
以上是脚本的第一部分，主要功能是检查是否有提供参数，如果没有，则输出使用方法并退出。接下来，脚本会处理用户提供的命令。

# 推送代码到github

如果您要将自己本地的代码推送到GitHub上，可以按照以下步骤操作：
1. **安装Git**：如果您的系统上还没有安装Git，请先安装它。例如，在基于Debian的系统上，您可以使用以下命令：
   ```bash
   sudo apt-get install git
   ```
2. **配置Git**：设置您的用户信息，这些信息将用于Git提交记录：
   ```bash
   git config --global user.name "您的用户名"
   git config --global user.email "您的邮箱"
   ```
3. **创建新的Git仓库**：在您的本地项目目录中初始化一个新的Git仓库：
   
   ```bash
   cd /path/to/your/project
   git init
   # 如果要重新初始化就要先删除一下.git文件，用下面的命令
   rm -rf .git 
   ```
4. **添加文件到仓库**：将您的代码文件添加到Git仓库：
   
   ```bash
   git add .
   ```
5. **提交更改**：提交您的更改，并添加一个提交信息：
   ```bash
   git commit -m "初始提交"
   ```
6. **在GitHub上创建新的仓库**：登录GitHub，创建一个新的仓库，不要初始化仓库，这样不会生成README文件或其他初始化文件。
7. **将本地仓库与GitHub仓库关联**：在本地仓库中添加一个远程仓库的引用，指向您在GitHub上创建的仓库：
   
   ```bash
   git remote add origin https://github.com/用户名/仓库名.git
   ```
8. **推送本地代码到GitHub**：将本地的代码推送到GitHub仓库：
   ```bash
   git push -u origin master
   ```
   如果您使用的是GitHub的SSH方式，则命令可能会有所不同，例如：
   ```bash
   git push -u origin main
   ```
   这里的`master`或`main`取决于您在GitHub上设置的默认分支名称。
   
   
   ---
   
   **切换分支**
   
   你可以使用以下命令来查看和切换分支：
   
   1. **查看所有分支**：
      ```bash
      git branch -a
      ```
   
   2. **切换到现有分支**：
      ```bash
      git checkout 分支名
      ```
   
   3. **创建并切换到新分支**：
      ```bash
      git checkout -b 新分支名
      ```
   
   如果你想从 `main` 分支新建一个分支，例如 `feature`，可以这样做：
   
   ```bash
   git checkout -b feature main
   ```
   
   这样你就会在新分支 `feature` 上继续开发工作了。
   
   ---
   
9. **确认上传完成**：在GitHub上检查您的仓库，确保代码已经成功上传。
请注意，如果您是在一个已经存在的本地Git仓库中工作，并且已经进行了提交，那么您可能需要先拉取GitHub上的最新代码，解决任何可能的冲突，然后才能推送您的更改。此外，如果您的项目非常大，或者包含敏感数据，您可能需要考虑使用Git LFS（Large File Storage）来管理大文件。

**如果本地代码有更新**

如果您已经在本地对代码进行了修改，并希望将这些更改更新到GitHub上，您可以按照以下步骤操作：
1. **切换到您的本地分支**：首先，确保您位于包含您更改的本地分支上。
   ```bash
   git checkout 分支名
   ```

2. **查看更改**：使用以下命令查看您做了哪些更改。
   ```bash
   git status
   ```

3. **添加更改**：将您想要提交的所有更改添加到暂存区。
   ```bash
   git add .
   ```
   这里的`.`代表添加所有更改，如果您只想添加特定文件，可以替换`.`为文件路径。

4. **提交更改**：创建一个新的提交，包含您的更改和一个描述性的提交信息。
   ```bash
   git commit -m "描述您的更改"
   ```

5. **推送到远程仓库**：将您的本地提交推送到GitHub上的远程仓库。如果您的默认分支是`main`，则使用：
   ```bash
   git push origin main
   ```
   如果您的默认分支是`master`，则使用：
   ```bash
   git push origin master
   ```

6. **解决合并冲突**（如有）：如果在推送时遇到合并冲突，您需要解决这些冲突后才能成功推送。这通常发生在多个人在同一分支上工作时。

7. **退回已提交的版本**：

   你可以通过以下方法在 Git 中回退到之前的版本：

   1. **查看提交历史**：
      - 右键点击你想要回退到的某个提交，然后选择“查看提交历史”或者类似选项，这样你可以确认到具体的提交哈希值。

   2. **回退到指定版本**：
      - 使用 Git 命令行，在项目目录中执行以下命令，假设你要回退到某个特定的提交（例如：`abc1234` 是该提交的哈希值）：
        ```bash
        git reset --hard abc1234
        ```
      - 使用 `git reset --hard` 会丢弃当前的所有更改并直接回到指定提交。

   3. **创建一个新的分支**（可选）：
      - 如果你不想影响当前分支的历史记录，可以创建一个新的分支。例如：
        ```bash
        git checkout -b new-branch-name abc1234
        ```
      - 这样会在指定的提交上创建一个新的分支，不影响当前的分支历史。

   4. **推送更改**：
      - 如果你已经将当前分支推送到了远程仓库，并且想要在远程仓库中反映这个回退，你需要强制推送：
        ```bash
        git push origin branch-name --force
        ```
      - 请谨慎使用 `--force` 参数，因为这会覆盖远程仓库的记录，可能会影响其他协作开发者。

   通过这些步骤，你可以回退到之前的任意版本。希望这能帮助到你！

   

记得写**忽略文件**`.gitignore`避免不必要的文件上传,例如：

```
log
log_*
*.png
*.rar
*.fig
*.mat
*.pyc
*.zip
*.pdf
*log*
*.pth
```

## 常见问题

1. **如何在某个文件夹下建立git**

   ### 解决方法

   要在特定文件夹中使用 Git 配置，首先需要将该文件夹初始化为一个 Git 仓库。可以按照以下步骤操作：

   1. **进入项目文件夹**：
      ```bash
      cd ~/project/xlx
      ```

   2. **初始化 Git 仓库**：
      在文件夹中运行以下命令，将其初始化为一个 Git 仓库：

      ```bash
      git init
      ```

      执行该命令后，Git 会创建一个 `.git` 文件夹，使该目录成为一个 Git 仓库。

   3. **设置本地用户名和邮箱**：
      然后，您可以在这个项目仓库中配置用户名和邮箱：

      ```bash
      git config user.name "kcraol1"
      git config user.email "您的邮箱@example.com"
      ```

   ### 验证配置

   您可以运行以下命令来查看配置是否生效：

   ```bash
   git config user.name
   git config user.email
   ```

   这样配置后，`user.name` 和 `user.email` 仅在当前仓库（`~/project/xlx`）中有效，不会影响其他仓库。

2. **怎么修改分支名称**

   是的，Git 可以修改分支名，有以下两种方法：修改当前分支的名称或修改其他分支的名称。

   ### 方法一：修改当前分支的名称
   1. 确保你已经切换到想要重命名的分支。
      ```bash
      git checkout <branch-name>
      ```
   2. 使用 `git branch -m` 命令重命名当前分支。
      ```bash
      git branch -m <new-branch-name>
      ```
      例如：
      ```bash
      git branch -m new-branch-name
      ```

   ### 方法二：修改其他分支的名称
   如果你需要修改一个**不是当前分支**的名称：
   1. 确保你当前不在要修改的分支上。
      例如，切换到 `main` 分支：
      ```bash
      git checkout main
      ```
   2. 使用 `git branch -m` 命令并指定旧分支名和新分支名：
      ```bash
      git branch -m <old-branch-name> <new-branch-name>
      ```
      例如：
      ```bash
      git branch -m old-branch-name new-branch-name
      ```

   ### 推送新的分支名称到远程仓库
   1. 删除远程旧分支（可选，但推荐），避免冗余：
      ```bash
      git push origin --delete <old-branch-name>
      ```
   2. 推送新的分支名称：
      ```bash
      git push origin <new-branch-name>
      ```
   3. 如果需要将本地新分支与远程分支关联：
      ```bash
      git branch --set-upstream-to=origin/<new-branch-name> <new-branch-name>
      ```

   ### 注意事项
   - 修改分支名后，团队成员需要更新本地仓库以避免混乱。
   - 在分支名称修改后，更新相关的 CI/CD 或脚本配置中对旧分支的引用。

3. **冲突合并**

   ---

   ### 背景
   当执行 `git pull` 时，它会尝试从远程分支拉取最新的更改并合并到你的本地分支。分歧可能发生的原因是：
   - 你在本地分支进行了提交，而远程分支也发生了更新。
   - 两边的提交历史并不线性，Git 无法直接快进（fast-forward）合并，需要你选择如何处理。

   ---

   ### 解决方法
   Git 提供了三种常用的合并策略，你可以根据需求选择一种：

   ---

   #### 1. **策略：Merge（默认，传统方式合并）**
   - 直接合并远程的更改到本地。
   - 这会保留分支的历史和分歧，可能产生一个新的“合并提交”（merge commit）。

   执行以下命令：
   ```bash
   git pull --no-rebase
   ```
   或者设置为默认合并策略（推荐）：
   ```bash
   git config pull.rebase false
   git pull
   ```

   ---

   #### 2. **策略：Rebase（变基，线性化历史）**
   - 把你的本地提交放到远程分支的最新提交之后，重新排列历史。
   - 适合需要保持提交历史干净的场景，但需要确保没有多人合作可能引起冲突。

   执行以下命令：
   ```bash
   git pull --rebase
   ```
   或者设置为默认变基策略：
   ```bash
   git config pull.rebase true
   git pull
   ```

   ---

   #### 3. **策略：Fast-forward only（仅快进合并，没有分歧时拉取）**
   - 如果本地分支可以简单地快进到远程分支（没有本地的独立提交），就执行拉取；否则报错。
   - 适用于严格控制分支历史的场景。

   执行以下命令：
   ```bash
   git pull --ff-only
   ```
   或者设置为默认策略：
   ```bash
   git config pull.ff only
   git pull
   ```

   ---

   ### 推荐做法
   如果你不确定使用哪种策略，可以尝试以下步骤：

   1. **检查本地和远程分支的状态**
      ```bash
      git fetch origin
      git status
      ```
      这将告诉你本地分支和远程分支有何差异。

   2. **选择合适的策略：**
      - 如果你想保留历史分歧，执行 `git pull --no-rebase`。
      - 如果你想让提交历史更整洁，执行 `git pull --rebase`。

   3. **解决冲突（如有）**
      如果在拉取时遇到冲突，Git 会提示你解决冲突。解决后，执行以下命令完成拉取：
      ```bash
      git add <conflicted-files>
      git rebase --continue  # 如果使用了 rebase
      git commit             # 如果使用了 merge
      ```

   ---

   ### 总结
   这个问题是因为 Git 不知道你希望如何处理分歧，你可以选择一种合并策略，或者全局设置默认策略：
   ```bash
   git config --global pull.rebase false  # 设置默认合并方式
   ```

# vscode远程连接

## ssh连接

安装扩展**ssh remote**（应该是叫这名字）

设置配置

```
Host s5808
  HostName 00.0000.000.000
  Port 6000
  User yang.liu
  IdentityFile "C:\Users\你的用户名\.ssh\id_rsa"

Host s5804
  HostName 172.99.99.99
  User luxi.xiao
  IdentityFile "C:\Users\你的用户名\.ssh\id_rsa"
  ProxyCommand C:\Windows\System32\OpenSSH\ssh.exe -W %h:%p -q s5808
 # Mac的跳板连接
  roxyCommand ssh -W %h:%p -q s5808
```

这是跳板连接

```
Host pgy_5804
  HostName 172.77.77.77
  User luxi.xiao
  IdentityFile "C:\Users\你的用户名\.ssh\id_rsa"
```

这是直接连接，`IdentityFile "C:\Users\你的用户名\.ssh\id_rsa"`是密钥，这部分可以查阅[ssh免密登录](#如何设置ssh免密登录)

## 重置服务器端的设置

直接删除`.vscode-sever`这个文件夹，简单粗暴

# 如何安装deb包

下载 `.deb` 包后，你可以使用 `dpkg` 或 `apt` 工具来安装它们。以下是安装 `.deb` 包的步骤：

## 使用 `dpkg` 安装 `.deb` 包

1. 打开终端。
2. 导航到你下载 `.deb` 包的目录。例如，如果你下载的文件在 `Downloads` 文件夹中，可以使用以下命令：
   ```bash
   cd ~/Downloads
   ```
3. 使用 `dpkg` 安装 `.deb` 包。假设你下载的文件名为 `tensorrt-7.x.x.x-ubuntu-18.04.deb`，你可以使用以下命令来安装它：
   ```bash
   sudo dpkg -i tensorrt-7.x.x.x-ubuntu-18.04.deb
   ```

4. 如果安装过程中出现依赖性错误，可以使用以下命令来修复它们：
   ```bash
   sudo apt-get install -f
   ```

## 使用 `apt` 安装 `.deb` 包

1. 打开终端。
2. 导航到你下载 `.deb` 包的目录：
   ```bash
   cd ~/Downloads
   ```
3. 使用 `apt` 安装 `.deb` 包。使用以下命令来安装下载的 `.deb` 包：
   ```bash
   sudo apt install ./tensorrt-7.x.x.x-ubuntu-18.04.deb
   ```

这两种方法都可以成功安装 `.deb` 包。安装完成后，你可以验证 TensorRT 是否已成功安装，并检查库文件是否在预期的位置。例如，你可以检查 `/usr/lib` 和 `/usr/include` 目录中是否有 TensorRT 相关的文件。

# 查看硬盘情况

如果你只想知道有多少硬盘空间被使用了，以及有多少硬盘空间是空闲的，使用 `df` 命令是最简单和直接的方法。你可以按照以下步骤操作：

1. 打开终端。

2. 输入以下命令并按回车：
   ```bash
   df -h
   ```

这将显示所有挂载点的磁盘使用情况，以人类可读的格式。输出示例如下：

```plaintext
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1       100G   60G   40G  60% /
udev            7.9G     0  7.9G   0% /dev
tmpfs           1.6G  9.8M  1.6G   1% /run
tmpfs           7.9G  104M  7.8G   2% /dev/shm
tmpfs           5.0M  4.0K  5.0M   1% /run/lock
tmpfs           7.9G     0  7.9G   0% /sys/fs/cgroup
```

在这个示例中，`/dev/sda1` 是主要的磁盘分区，你可以看到它的总大小是 100G，已经使用了 60G，还剩下 40G 可用空间，使用率是 60%。

你可以根据你的系统的实际输出，查看各个挂载点的使用情况。通常最关心的是根文件系统（`/`）的使用情况。

# smb分享文件

要在Linux系统上设置SMB共享文件，可以按照以下步骤进行：

### 1. 安装Samba
首先，确保系统已经安装了Samba。你可以使用以下命令进行安装：

```bash
sudo apt update
sudo apt install samba
```

### 2. 配置Samba
编辑Samba配置文件`smb.conf`，通常位于`/etc/samba/smb.conf`。

```bash
sudo nano /etc/samba/smb.conf
```

在文件末尾添加以下内容来定义一个共享文件夹。例如：

```ini
[shared]
   path = /home/yourusername/shared
   available = yes
   valid users = yourusername
   read only = no
   browsable = yes
   public = yes
   writable = yes
```

### 3. 创建共享文件夹
创建你打算共享的文件夹，并设置适当的权限：

```bash
mkdir -p /home/yourusername/shared
chmod 777 /home/yourusername/shared # 实际操作下来可以不用这一步
```

### 4. 添加Samba用户
添加用户到Samba并设置密码：

**添加的用户必须是那台机器上已有的用户**

```bash
sudo smbpasswd -a yourusername
```

### 5. 重启Samba服务
每次修改Samba配置文件后，都需要重启Samba服务：

```bash
sudo systemctl restart smbd
sudo systemctl restart nmbd
```

### 6. 访问共享文件
在其他设备上，可以通过以下方式访问共享文件：

- 在Windows上，打开文件资源管理器，输入`\\<Linux服务器IP地址>\shared`。
- 在Mac上连接SMB共享文件夹可以按照以下步骤进行：

  ### 1. 打开“连接服务器”对话框
  1. 打开Finder。
  2. 在顶部菜单栏中，点击“前往”菜单。
  3. 从下拉菜单中选择“连接服务器…”（或者使用快捷键 `Command + K`）。

  ### 2. 输入服务器地址
  在“连接服务器”对话框中，输入SMB服务器的地址。地址格式如下：

  ```
  smb://<服务器IP地址>/<共享文件夹名称>
  ```

  例如，如果服务器IP地址是`192.168.1.10`，共享文件夹名称是`shared`，那么输入：

  ```
  smb://192.168.1.10/shared
  ```

  ### 3. 连接到服务器
  点击“连接”按钮。系统会提示你输入凭据。

  ### 4. 输入凭据
  在弹出的对话框中，输入你的用户名和密码（这是在Linux服务器上配置的Samba用户），然后点击“连接”。

  ### 5. 访问共享文件夹
  连接成功后，共享文件夹会像本地磁盘一样显示在Finder的侧栏中。你可以像操作本地文件一样访问和操作共享文件。

  ### 其他注意事项：
  - **网络可达性**：确保Mac和Linux服务器在同一网络内，并且Mac能够访问Linux服务器的IP地址。
  - **防火墙设置**：如果Linux服务器上有防火墙，请确保开放了用于SMB的端口（通常是TCP端口445和139）。
  - **共享文件夹权限**：确保共享文件夹设置了适当的权限，以便Samba用户可以读写文件。

  通过以上步骤，你应该能够在Mac上成功连接到Linux上的SMB共享文件夹。如果在连接过程中遇到任何问题，请提供更多细节以便进一步诊断和解决。
- 在Linux上，可以使用以下命令挂载共享文件夹：

```bash
sudo mount -t cifs //Linux服务器IP地址/shared /mnt（本机目录） -o username=yourusername
```

确保替换所有示例中的`yourusername`和`Linux服务器IP地址`为实际的用户名和服务器IP地址。

### 自动挂载（可选）

为了在系统启动时自动挂载SMB共享，可以在`/etc/fstab`文件中添加一行配置：

```bash
//smb-server/share /mnt/smb_share cifs username=username,password=password,domain=domain(可省略) 0 0
```

请注意，密码会以明文形式保存在`/etc/fstab`中，可能会有安全风险。可以使用`credentials`文件来避免明文密码。

### 使用credentials文件（可选）

1. 创建`credentials`文件：
   ```bash
   sudo nano /etc/samba/credentials
   ```

2. 在文件中添加以下内容:

   ```bash
   username=username
   password=password
   domain=domain
   ```

3. 修改文件权限以确保安全：
   ```bash
   sudo chmod 600 /etc/samba/credentials
   ```

4. 在`/etc/fstab`中使用`credentials`文件：
   ```bash
   //smb-server/share /mnt/smb_share cifs credentials=/etc/samba/credentials 0 0
   ```

### 断开挂载点

断开挂载（卸载）已经挂载的SMB共享文件夹非常简单，可以使用`umount`命令。以下是详细步骤：

#### 1. 找到挂载点

假设你之前挂载的路径是`/公共的/test`。

#### 2. 卸载挂载点

使用以下命令卸载该挂载点：

```sh
sudo umount /公共的/test
```

#### 注意事项

1. 确保没有任何程序或用户正在使用挂载的目录，否则卸载可能会失败。
2. 如果你想查看当前所有挂载点，可以使用以下命令：

```sh
mount | grep cifs
```

这个命令会列出所有使用CIFS（SMB协议）挂载的文件系统。

## 常用命令

添加用户密码

```bash
sudo smbpasswd -a xlx
```

重置密码

```bash
sudo smbpasswd xlx
```

检查用户

```bash
sudo pdbedit -L
```

查看指定用户

```bash
sudo pdbedit -Lv xlx
```

删除用户

```bash
sudo smbpasswd -x xlx
```

检查状态

```bash
sudo systemctl status smbd
sudo systemctl status nmbd
```

查看日志

```bash
sudo tail -f /var/log/samba/log.smbd
```

创建用户组

```bash
sudo groupadd sambashare
```

将用户添加到组

```bash
sudo usermod -aG sambashare username1
sudo usermod -aG sambashare username2
sudo usermod -aG sambashare username3
```

更改共享文件夹所有者

```bash
sudo chown -R :sambashare /home/shared
```

配置文件

```bash
[shared]
   path = /home/shared
   available = yes
   valid users = @sambashare
   read only = no
   browsable = yes
   public = no
   writable = yes
   # 实际操作中可以不要下面两行
   create mask = 0660
   directory mask = 0770
```

# 本地多用户共享文件

在Linux系统中，如果你想让多个用户访问同一个文件夹，可以通过设置组权限来实现。以下是具体步骤：

1.  **创建一个新的用户组**：
   ```sh
   sudo groupadd sharedgroup
   ```

2. **将所有需要访问该文件夹的用户添加到这个组中**：
   ```sh
   sudo usermod -aG sharedgroup username1
   sudo usermod -aG sharedgroup username2
   # 对所有需要访问的用户执行以上命令
   ```

3. **设置文件夹的所属组**：
   
   ```sh
   sudo chown :sharedgroup /path/to/sharedfolder
   ```
   
4. **设置文件夹的权限**，使组内用户可以访问：
   ```sh
   sudo chmod 770 /path/to/sharedfolder
   ```
   或者，如果你想允许所有组成员可以读写该文件夹但不执行：
   ```sh
   sudo chmod 660 /path/to/sharedfolder
   ```

5. **确保文件夹内新创建的文件和子文件夹也继承这些权限**：
   ```sh
   sudo chmod g+s /path/to/sharedfolder
   ```

这样，所有被添加到`sharedgroup`组中的用户就可以访问并操作`/path/to/sharedfolder`文件夹中的内容了。

**说明**：
- `groupadd`命令用于创建一个新的组。
- `usermod -aG`命令用于将用户添加到指定的组。
- `chown :sharedgroup`命令用于改变文件夹的所属组。
- `chmod 770`设置文件夹的权限，使文件夹的所有者和组内成员可以读写和执行该文件夹中的内容，而其他用户无法访问。
- `chmod g+s`设置“setgid”位，这样新创建的文件和子文件夹将继承父文件夹的组。

# 设置软连接

设置完共享权限后，如果你希望不同用户方便地访问共享文件夹，确实可以通过创建软链接（符号链接）来简化访问路径。以下是具体步骤：

### 1. 创建软链接

假设你的共享文件夹路径为 `/path/to/sharedfolder`，你可以在每个用户的主目录下创建一个指向该共享文件夹的软链接。例如：

```sh
ln -s /path/to/sharedfolder /home/username/sharedfolder
```

对于每个用户执行上述命令，将 `username` 替换为实际的用户名。

### 2. 示例

如果共享文件夹路径为 `/home/shared/everycan`，并且你想让用户 `yang` 方便访问：

```sh
ln -s /home/shared/everycan /home/yang/everycan
```

这样，`yang` 用户就可以通过访问其主目录中的 `everycan` 软链接来访问共享文件夹。

### 3. 检查软链接

确认软链接创建成功，并且用户可以通过软链接访问共享文件夹：

```sh
ls -l /home/yang/everycan
```

输出应该类似于：

```sh
lrwxrwxrwx 1 yang yang 20 Jul 22 08:00 /home/yang/everycan -> /home/shared/everycan
```

### 4. 权限检查

确保共享文件夹及其内容的权限设置正确，以允许组成员访问：

```sh
sudo chmod -R 770 /home/shared/everycan
```

确认共享文件夹的所属组，并确保所有需要访问的用户都在该组中：

```sh
sudo chown -R :sharedgroup /home/shared/everycan
```

# 查看主板信息

在 Linux 系统中，有多种方法可以查看主板信息。以下是几种常用的方法：

### 使用 `dmidecode` 命令
`dmidecode` 是一个用于查看系统硬件信息的命令，可以显示详细的主板信息。

1. 安装 `dmidecode`（如果尚未安装）：
   ```bash
   sudo apt-get install dmidecode   # 对于基于 Debian 的系统，如 Ubuntu
   sudo yum install dmidecode       # 对于基于 Red Hat 的系统，如 CentOS
   ```

2. 运行以下命令查看主板信息：
   ```bash
   sudo dmidecode -t 2
   ```
   该命令会输出主板的制造商、型号、版本和序列号等信息。

### 使用 `lshw` 命令
`lshw` 是另一个强大的硬件信息查看工具。

1. 安装 `lshw`（如果尚未安装）：
   ```bash
   sudo apt-get install lshw        # 对于基于 Debian 的系统
   sudo yum install lshw            # 对于基于 Red Hat 的系统
   ```

2. 运行以下命令查看主板信息：
   ```bash
   sudo lshw -class motherboard
   ```
   该命令会输出主板的详细信息。

### 使用 `hwinfo` 命令
`hwinfo` 是另一个硬件信息查看工具，特别适用于详细的硬件分析。

1. 安装 `hwinfo`（如果尚未安装）：
   ```bash
   sudo apt-get install hwinfo      # 对于基于 Debian 的系统
   sudo yum install hwinfo          # 对于基于 Red Hat 的系统
   ```

2. 运行以下命令查看主板信息：
   ```bash
   sudo hwinfo --motherboard
   ```
   该命令会输出主板的详细信息。

### 使用 `inxi` 命令
`inxi` 是一个功能强大的系统信息脚本，可以显示简洁的硬件信息。

1. 安装 `inxi`（如果尚未安装）：
   ```bash
   sudo apt-get install inxi        # 对于基于 Debian 的系统
   sudo yum install inxi            # 对于基于 Red Hat 的系统
   ```

2. 运行以下命令查看主板信息：
   ```bash
   inxi -M
   ```
   该命令会输出主板的基本信息。

# 设置开机任务

```bash
sudo nano /etc/systemd/system/your_service_name.service
```

填写配置

```bash
[Unit]
Description=Your Service Description
After=network.target

[Service]
ExecStart=/path/to/your_command

[Install]
WantedBy=multi-user.target

```

保存退出

```bash
sudo systemctl enable your_service_name.service
sudo systemctl start your_service_name.service
```

查看日志

```bash
sudo journalctl -u your_service_name.service -b
```

一般会遇到权限问题，设置为所有人都可读写即可

# 远程端口转发

要在远程控制终端通过SSH访问本地的Clash Dashboard，可以使用SSH的端口转发功能。假设你希望在远程主机上访问本地127.0.0.1:9090的Clash Dashboard，以下是步骤：

### 1. **使用SSH本地端口转发**

在你远程登录到服务器时，可以使用以下命令将远程主机的一个端口转发到本地的Clash Dashboard：

```bash
ssh -L <remote_port>:127.0.0.1:9090 <username>@<remote_host>
```

- `<remote_port>`：在远程主机上用于访问的端口号。例如，可以选择8080。
- `<username>`：你的远程主机的用户名。
- `<remote_host>`：远程主机的IP地址或域名。

例如，如果你选择在远程主机上使用8080端口，并且远程主机的IP地址是192.168.1.100，用户名是`user`，你可以这样做：

```bash
ssh -L 8080:127.0.0.1:9090 user@192.168.1.100
```

### 2. **访问Clash Dashboard**

在SSH连接成功后，你可以在远程主机的浏览器中访问以下URL来打开Clash Dashboard：

```
http://127.0.0.1:8080
```

这个操作将127.0.0.1:8080映射到本地127.0.0.1:9090，从而可以在远程主机的浏览器中访问Clash Dashboard。

### 3. **注意事项**

- 确保你的SSH客户端和远程主机之间的网络连接正常，并且没有防火墙或安全组阻止所选的远程端口。
- 如果远程主机没有GUI环境，你可以使用类似`ssh -L`的方式在本地主机上映射并使用浏览器访问。

这样，你就可以通过远程SSH访问和操作本地的Clash Dashboard。

---

**常见问题**

1. 怎么撤回这些操作？

   要撤回通过SSH进行的端口转发操作，只需要断开SSH连接即可。以下是步骤：

   1. **断开SSH连接：**
      如果你是在终端中启动的SSH会话（例如，使用`ssh -L`命令），只需在终端中按下`Ctrl + C`或输入`exit`命令即可断开连接。这样，所有的端口转发都会立即停止。

   2. **关闭指定的端口转发：**
      如果你想单独关闭特定的端口转发，可以在终端中查看所有的SSH会话并终止它们。例如，使用以下命令来列出所有SSH进程：
      ```bash
      ps aux | grep ssh
      ```
      然后，你可以使用`kill`命令终止特定的SSH进程。例如，如果找到某个SSH进程的PID是1234，可以使用：
      ```bash
      kill 1234
      ```
      终止该进程。

   3. **确认端口转发已停止：**
      你可以尝试在浏览器中访问先前设置的远程端口。如果已经无法访问，则表示端口转发已经成功撤回。

   这样，就可以撤回之前通过SSH设置的端口转发操作。

# 实时查看显卡占用情况

```bash
watch -n 0.5 nvidia-smi
```

# 换源

```bash
# 清华
pip install torch -i https://pypi.tuna.tsinghua.edu.cn/simple
# 阿里
pip install torch -i https://mirrors.aliyun.com/pypi/simple
```

# 使用日期生成文件名

```bash
python -u demo7.py > log_$(date +"%Y%m%d_%H%M%S").log 2>&1 &
```

# 创建文件

在 Linux 中，有几种不同的方法可以创建文件：

### 1. 使用 `touch` 命令
```bash
touch 文件名
```
例如：
```bash
touch myfile.txt
```
这会创建一个空的 `myfile.txt` 文件。如果文件已经存在，`touch` 还可以更新文件的时间戳。

### 2. 使用 `echo` 命令
```bash
echo "内容" > 文件名
```
例如：
```bash
echo "Hello, World!" > myfile.txt
```
这会创建一个包含 "Hello, World!" 的 `myfile.txt` 文件。如果文件已经存在，`>` 会覆盖文件内容。使用 `>>` 可以追加内容而不覆盖原文件。

### 3. 使用 `cat` 命令
```bash
cat > 文件名
```
然后输入内容，按 `Ctrl + D` 结束输入。

例如：
```bash
cat > myfile.txt
```
输入内容后，按 `Ctrl + D` 保存并退出。

### 4. 使用 `nano` 或其他文本编辑器
打开编辑器新建文件，输入内容后保存即可。
```bash
nano 文件名
```
例如：
```bash
nano myfile.txt
```

这些方法都可以用于创建新文件，你可以选择适合自己的方式。



# 多个视频合成一个

在 Linux 中，可以使用 `ffmpeg` 来将多个 MP4 文件合成一个。下面是如何操作的步骤：

### 1. 安装 `ffmpeg`
如果你的系统还没有安装 `ffmpeg`，可以通过以下命令安装：

- 在 Ubuntu/Debian 系统上：
  ```bash
  sudo apt update
  sudo apt install ffmpeg
  ```

- 在 CentOS/Fedora 系统上：
  ```bash
  sudo yum install ffmpeg
  ```

### 2. 创建一个文本文件
将你想合成的 MP4 文件列表写入一个文本文件，文件名可以是 `file_list.txt`，内容格式如下：

```
file 'file1.mp4'
file 'file2.mp4'
file 'file3.mp4'
```

### 3. 使用 `ffmpeg` 合成文件
在终端中运行以下命令：

```bash
ffmpeg -f concat -safe 0 -i file_list.txt -c copy output.mp4
```

### 解释：
- `-f concat`：指定合成模式为合并文件。
- `-safe 0`：允许使用相对路径（如果路径中有特殊字符或空格）。
- `-i file_list.txt`：指定输入的文件列表。
- `-c copy`：复制视频和音频流，而不重新编码。
- `output.mp4`：指定输出文件名。

这样就可以将多个 MP4 文件合并成一个新的 MP4 文件。

# `ed25519`和`RSA(4096)`

`ed25519` 和 `RSA (4096)` 是两种不同的加密算法，它们各自有独特的特点和使用场景。以下是两者的区别和对比：

---

## 1. **算法类型**
- **`ed25519`**:
  - 使用基于椭圆曲线的签名算法（Elliptic Curve Digital Signature Algorithm，ECDSA）。
  - Ed25519 是具体实现的一种，基于 Curve25519 椭圆曲线。
  - 更现代的加密方法，相比 RSA 更高效。

- **`RSA (4096)`**:
  - 基于大整数分解问题的传统非对称加密算法。
  - 算法成熟、历史悠久，广泛使用于很多老旧系统。

---

## 2. **密钥长度**
- **`ed25519`**:
  - 密钥长度固定为 **256 位**。
  - 不需要更长的密钥，因为基于椭圆曲线的算法提供了更高的安全性。

- **`RSA`**:
  - 密钥长度可以是 2048 位、3072 位或 4096 位等。
  - **4096 位 RSA 密钥**比 2048 位更安全，但生成和验证效率较低。

---

## 3. **性能**
- **`ed25519`**:
  - 计算效率高，尤其是在签名生成和验证操作中。
  - 私钥和公钥都更小，存储和传输效率更高。
  - 非常适合资源受限的设备（如嵌入式设备或 IoT）。

- **`RSA`**:
  - 在密钥长度增加时，计算开销成倍增长。
  - 签名和加解密操作速度较慢，但兼容性更好。
  - 由于算法复杂，密钥长度较长，占用更多存储空间。

---

## 4. **安全性**
- **`ed25519`**:
  - 基于椭圆曲线的算法，比等效长度的 RSA 提供更高的安全性。
  - **256 位的 Ed25519 密钥的安全性**相当于 **3072 位的 RSA 密钥**。

- **`RSA`**:
  - 安全性依赖于密钥长度（例如，2048 位的 RSA 密钥未来可能会被破解）。
  - **4096 位 RSA 密钥**目前非常安全，但计算成本较高。

---

## 5. **兼容性**
- **`ed25519`**:
  - 支持较新的系统和应用程序。
  - 并非所有老旧的 SSH 或系统工具都支持 Ed25519。例如，某些旧的 OpenSSH 版本可能不支持。

- **`RSA`**:
  - 几乎所有系统都支持 RSA。
  - 适合与老旧系统交互或需要最大兼容性的场景。

---

## 6. **使用场景**
- **`ed25519`**:
  - 首选现代安全性要求较高的场景。
  - 更适合新系统、性能敏感的环境或资源受限的设备。

- **`RSA (4096)`**:
  - 推荐用于需要最大兼容性和与旧系统交互的场景。
  - 如果对性能没有特别要求，可以使用 4096 位 RSA 密钥作为安全性较高的选择。

---

## 7. **密钥文件大小**
- **`ed25519`**:
  - 私钥和公钥文件都很小，通常只有几百字节。
  - 更节省存储空间。

- **`RSA`**:
  - 私钥和公钥文件更大，4096 位的 RSA 密钥可能达到几 KB。
  - 在大规模部署时，文件大小可能成为问题。

---

### 总结

| 特性         | Ed25519            | RSA (4096)            |
| ------------ | ------------------ | --------------------- |
| **算法类型** | 椭圆曲线算法       | 大整数分解算法        |
| **密钥长度** | 固定 256 位        | 可选（4096 位更安全） |
| **性能**     | 高效，适合现代设备 | 慢，性能较低          |
| **安全性**   | 更高的安全性       | 安全但依赖更长密钥    |
| **兼容性**   | 支持较新系统       | 老旧系统支持更好      |
| **文件大小** | 小                 | 大                    |

**推荐选择：**
- 如果需要性能和现代安全性，选择 **Ed25519**。
- 如果需要兼容性或与老旧系统交互，选择 **RSA (4096)**。
- 对于一般使用，Ed25519 是目前的首选。

# 运行Python如何查找PID

在运行 Python 脚本后，可以通过以下几种方式获取它的进程 ID（PID）：

---

### 方法 1：直接在运行时获取 PID
在 `train.py` 中添加以下代码，运行时会直接打印出当前脚本的 PID：

```python
import os
print(f"Process ID (PID): {os.getpid()}")
```

运行脚本时会在终端输出它的 PID。

---

### 方法 2：通过 `ps` 命令查找
1. 打开一个新的终端。
2. 使用以下命令查找运行中的 `train.py` 的 PID：
   ```bash
   ps aux | grep train.py
   ```
   输出可能类似：
   ```
   username   12345  0.0  0.1  123456  7890 pts/1    S+   10:00   0:00 python train.py
   ```
   **12345** 就是 PID。

---

### 方法 3：通过 `pgrep` 命令快速查找
如果知道脚本名称，可以直接使用以下命令：
```bash
pgrep -f train.py
```
这会返回与 `train.py` 匹配的 PID。

---

### 方法 4：任务管理器（GUI）
如果你使用的是带图形界面的操作系统，可以：
1. 打开任务管理器（Windows）或活动监视器（macOS），或者使用 `htop`（Linux）。
2. 找到 `python train.py` 的进程，查看它的 PID。

---

### 注意事项
- 如果你的脚本运行得很快，可能在你查找 PID 前已经完成，可以使用 `sleep` 延长运行时间。
- 如果运行多个相同脚本，需通过参数或环境变量区分它们。

# grep命令用法

`grep` 是 Linux 中用于搜索文件内容的强大工具，支持通过模式匹配查找文本。以下是 `grep` 命令的基本用法及常见选项：

---

### **基本语法**
```bash
grep [选项] "模式" 文件名
```

### **常用选项**
1. **`-i`**：忽略大小写
   ```bash
   grep -i "hello" file.txt
   ```
   查找 `file.txt` 中所有包含 `hello`（大小写不限）的行。

2. **`-n`**：显示匹配行的行号
   ```bash
   grep -n "error" file.log
   ```
   输出 `file.log` 中包含 `error` 的行及其行号。

3. **`-v`**：反向匹配（显示不符合模式的行）
   ```bash
   grep -v "success" file.log
   ```
   显示 `file.log` 中不包含 `success` 的行。

4. **`-r` 或 `-R`**：递归搜索目录
   ```bash
   grep -r "function" ./src
   ```
   在 `./src` 目录及其子目录中递归查找 `function`。

5. **`-l`**：只输出匹配的文件名
   ```bash
   grep -l "TODO" *.c
   ```
   显示当前目录下所有 `.c` 文件中包含 `TODO` 的文件名。

6. **`-c`**：统计匹配行的数量
   ```bash
   grep -c "error" file.log
   ```
   输出 `file.log` 中包含 `error` 的行数。

7. **`-w`**：精确匹配整个单词
   ```bash
   grep -w "main" file.c
   ```
   匹配 `main`，而不会匹配 `mainly` 或 `domain`。

8. **`-E`**：支持扩展正则表达式（等同于 `egrep`）
   ```bash
   grep -E "error|warning" file.log
   ```
   匹配 `error` 或 `warning`。

9. **`-o`**：只输出匹配的部分
   ```bash
   grep -o "https://[a-zA-Z0-9./?=_-]*" file.txt
   ```
   从文件中提取所有 URL。

10. **`--color`**：高亮显示匹配部分（多数情况下自动启用）
    ```bash
    grep --color "test" file.txt
    ```

---

### **常见用法示例**

1. **在文件中搜索字符串**
   ```bash
   grep "root" /etc/passwd
   ```

2. **递归搜索多个文件**
   ```bash
   grep -r "error" /var/log/
   ```

3. **结合管道符过滤命令输出**
   ```bash
   ps aux | grep "nginx"
   ```

4. **从日志中过滤关键词**
   ```bash
   tail -f /var/log/syslog | grep "error"
   ```

5. **查找多种模式**
   ```bash
   grep -E "error|fail" file.log
   ```

6. **使用正则匹配开始或结束的行**
   - 匹配以 `error` 开头的行：
     ```bash
     grep "^error" file.log
     ```
   - 匹配以 `done` 结尾的行：
     ```bash
     grep "done$" file.log
     ```

---

### **总结**
- `grep` 是一个基础但强大的文本搜索工具，结合正则表达式可以完成复杂的文本过滤任务。
- 当需要更复杂的功能时，可以结合 `awk` 或 `sed` 使用。

