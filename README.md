# OpenHarmony OS 5.1 Standard Build

This is an attempt to build from source **OpenHarmony OS 5.1 Standard**. 

IMP NOTE: The 3.2 build (old docker file) is working correctly. But 5.1 build has some build issues that I'm currently working out (mostly dependencies, flags, etc)

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
Machine Translated to Chinese:

# OpenHarmony OS 5.1 标准构建

这是一次从源代码**构建 OpenHarmony OS 5.1 标准版本**的尝试。

IMP注意：3.2构建（旧docker文件）工作正常。 但是5.1build有一些我目前正在解决的构建问题（主要是依赖关系，标志等）

## 目标

**主要目标：** 成功构建 OpenHarmony 5.1。

**附加目标：**

- 实现 GUI 交互  
- 支持小型 / 微型 / 资源受限设备的构建  
- 进一步探索系统能力  

## 使用的技术

我们正在使用 Docker、Docker Compose、QEMU、noVNC 等技术，以便更好地支持 GUI 运行。

## 项目结构

- `docker_old/` 文件夹中包含一个旧版 Dockerfile，它紧跟官方教程但基于 2023 年的过时版本 3.2，仅供参考。  
- 由于此前从 Gitee 获取源码时遇到网络问题，我们改为使用官方提供的 tar 包源码存档。
- 警告大约需要250-400GB的空间，尽管编译完成后的最终图像要小得多

## 参考资料

- **源码链接：** [OpenHarmony v5.1.0 发布说明](https://docs.openharmony.cn/pages/v5.1/en/release-notes/OpenHarmony-v5.1.0-release.md)  
- **过时的 Docker 教程：** [获取工具和源码](https://docs.openharmony.cn/pages/v5.1/en/device-dev/get-code/gettools-acquire.md)

## 贡献

欢迎随时提出问题、建议或改进想法！
