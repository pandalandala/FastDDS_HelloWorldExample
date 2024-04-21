# FastDDS_HelloWorldExample

1. ### 1. File Tree

    You should download this project on your own in section A2.

        .
        └── workspace_DDSHelloWorld
            ├── build
            ├── CMakeLists.txt
            └── src
                ├── HelloWorld.cxx
                ├── HelloWorld.h
                ├── HelloWorld.idl
                ├── HelloWorldCdrAux.hpp
                ├── HelloWorldCdrAux.ipp
                ├── HelloWorldPublisher.cpp
                ├── HelloWorldPubSubTypes.cxx
                ├── HelloWorldPubSubTypes.h
                └── HelloWorldSubscriber.cpp

    ### 2. Environment and Start

    1. OS: Windows 10/11

    2. IDE: Visual Studio **2022** (with `Desktop development with C++`)

    3. [eProsima Fast DDS installing](https://eprosima.com/index.php/downloads-all).

       - Tick all boxes of environment variable setup.
       - Recommend changing the folder name to `fastrtps`, which has no spacing.

    4. [CMake installing](https://cmake.org/download/). Recommend: `Windows x64 Installer: cmake-3.29.0-windows-x86_64.msi`. Run the `.msi` file.

    5. [Chocolatey installing](https://chocolatey.org/). Just run the following commands:

       ```
       Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
       ```

    6. Install dependencies just by clicking: [Asio](https://github.com/ros2/choco-packages/releases/download/2020-02-24/asio.1.12.1.nupkg), [TinyXML2](https://github.com/ros2/choco-packages/releases/download/2020-02-24/tinyxml2.6.0.0.nupkg).

    7. After downloading these packages, open an administrative shell with PowerShell and execute the following command:

       ```
       choco install -y -s <PATH_TO_DOWNLOADS> asio tinyxml2
       ```

       where `<PATH_TO_DOWNLOADS>` is the folder into which the packages have been downloaded.

    8. OpenSSL is a robust toolkit for the TLS and SSL protocols and a general-purpose cryptography library. Install it by running the following command inside an administrative shell with PowerShell:

       ```
       choco install -y openssl
       ```

       Make sure to configure your system variables:

       <img src="assets/image.png" div align=center />

       <img src="assets/image-1.png" div align=center style="zoom:80%;" />

    9. Run following commands in `build/`:

       ```
       cmake ..
       cmake --build .
       cd build/Debug/
       DDSHelloWorldPublisher.exe
       DDSHelloWorldSubscriber.exe
       ```

    10. Succeed!
