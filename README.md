# OpenHarmony OS 5.1 Standard Build

This is an attempt to build from source **OpenHarmony OS 5.1 Standard**. 

IMP NOTE: The 3.2 build (old docker file) is working correctly. But 5.1 build has some build issues that I'm currently working out (mostly dependencies, flags, etc)

## Steps to use
1. Clone the repo or just Download the 'Dockerfile.openharmony_standard' and 'docker-compose.yml' files
2. Download the source code tar archive from the official OpenHarmony site: https://repo.huaweicloud.com/openharmony/os/5.1.0-Release/code-v5.1.0-Release.tar.gz
3. Move the downloaded source code tar archive (without extracting) to the same directory as the Dockerfile.openharmony_standard and docker-compose.yml files such that the directory structure looks like this:
   ```
   .
   ├── Dockerfile.openharmony_standard
   ├── docker-compose.yml
   └── code-v5.1.0-Release.tar.gz
   ```
4. Open Terminal in vscode (or other editor)
5. Change Directory to the folder containing the dockerfile + compose file + source code tar archive
6. Run the command `docker-compose build openharmony_standard --no-cache --progress=plain` and it will start building. (Note: `--no-cache` is used to clear up previous build cache, and `--progress=plain` gives more detailed output)

Note: have 250-400GB space ideally. Download of source code alone is 49GB plus other dependencies, so it can take time depending on your internet speed. Also, as with any building from source, it will take time to build files.

Note: Consider running `docker system prune -a --force` to clear up unused docker images and free up space after the build is done.

## Goals

**Primary Goal:** Successfully build OpenHarmony 5.1

**Additional Goals:** 
- GUI interaction
- Build for Mini/Micro/Resource constrained devices
- Further exploration

## Technologies Used

We are using additional technologies like Docker, Docker Compose, QEMU, noVNC, etc. to help get a GUI running as well.

## Project Structure

- In the `docker_old/` folder, there is an old Dockerfile that follows the official tutorial closely, but it is outdated version 3.2 (from year 2023). It's just there for additional reference.
- Since we got networking issues before when getting source files from Gitee, we are using the officially provided tar archive.
- WARNING 250-400 GB space needed roughly, though the final image once the compiling is done is much smaller

## References

- **Source code** links were taken from here: https://docs.openharmony.cn/pages/v5.1/en/release-notes/OpenHarmony-v5.1.0-release.md
- **Outdated Docker** tutorial exists here: https://docs.openharmony.cn/pages/v5.1/en/device-dev/get-code/gettools-acquire.md

## Contributing

Feel free to open an issue to suggest refinements, ideas, etc. 

______

Machine Translated Chinese Version below (Excuse me for any inaccuracies)
______
## 中文版本

# OpenHarmony OS 5.1 标准构建

这是从源代码构建 **OpenHarmony OS 5.1 标准版** 的尝试。

重要提示：3.2 版本的构建（旧 Docker 文件）运行正常。但 5.1 版本的构建存在一些我目前正在解决的构建问题（主要是依赖项、标志等）

## 使用步骤
1. 克隆此仓库或直接下载 'Dockerfile.openharmony_standard' 和 'docker-compose.yml' 文件
2. 从官方 OpenHarmony 网站下载源代码 tar 归档文件：https://repo.huaweicloud.com/openharmony/os/5.1.0-Release/code-v5.1.0-Release.tar.gz
3. 将下载的源代码 tar 归档文件（不要解压）移动到与 Dockerfile.openharmony_standard 和 docker-compose.yml 文件相同的目录中，使目录结构如下所示：
   ```
   .
   ├── Dockerfile.openharmony_standard
   ├── docker-compose.yml
   └── code-v5.1.0-Release.tar.gz
   ```
4. 在 VSCode（或其他编辑器）中打开终端
5. 切换到包含 dockerfile + compose 文件 + 源代码 tar 归档文件的文件夹
6. 运行命令 `docker-compose build openharmony_standard --no-cache --progress=plain`，开始构建。（注意：`--no-cache` 用于清除之前的构建缓存，`--progress=plain` 提供更详细的输出）

注意：理想情况下需要 250-400GB 空间。仅源代码下载就有 49GB，加上其他依赖项，因此根据您的网速可能需要一些时间。另外，与任何从源代码构建一样，编译文件需要时间。

注意：构建完成后，可以运行 `docker system prune -a --force` 来清理未使用的 Docker 镜像并释放空间。

## 目标

**主要目标：** 成功构建 OpenHarmony 5.1

**附加目标：**
- GUI 交互
- 为 Mini/Micro/资源受限设备构建
- 进一步探索

## 使用的技术

我们使用 Docker、Docker Compose、QEMU、noVNC 等附加技术来帮助运行 GUI。

## 项目结构

- 在 `docker_old/` 文件夹中，有一个密切遵循官方教程的旧 Dockerfile，但它是过时的版本 3.2（2023年）。仅供参考。
- 由于我们之前从 Gitee 获取源文件时遇到网络问题，因此我们使用官方提供的 tar 归档文件。
- 警告：大约需要 250-400 GB 空间，尽管编译完成后的最终镜像要小得多

## 参考资料

- **源代码** 链接来自这里：https://docs.openharmony.cn/pages/v5.1/en/release-notes/OpenHarmony-v5.1.0-release.md
- **过时的 Docker** 教程在这里：https://docs.openharmony.cn/pages/v5.1/en/device-dev/get-code/gettools-acquire.md

## 贡献

欢迎提出问题来建议改进、想法等。