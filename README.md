# OpenHarmony OS 5.1 Standard Build

This is an attempt to build from source **OpenHarmony OS 5.1 Standard**.

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

## References

- **Source code** links were taken from here: https://docs.openharmony.cn/pages/v5.1/en/release-notes/OpenHarmony-v5.1.0-release.md
- **Outdated Docker** tutorial exists here: https://docs.openharmony.cn/pages/v5.1/en/device-dev/get-code/gettools-acquire.md

## Contributing

Feel free to open an issue to suggest refinements, ideas, etc. 
