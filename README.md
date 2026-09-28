# C语言学习网站

一个完整的 C/C++ 学习网站，支持在浏览器中直接编译和运行代码。

## 功能特性

### C 语言支持
- ✅ 完整的 C 语言解释器（纯 JavaScript 实现）
- ✅ printf / scanf
- ✅ 标准输入（stdin）
- ✅ for / while / do-while 循环
- ✅ if / else 条件判断
- ✅ 数组
- ✅ 函数
- ✅ 编译错误提示

### C++ 支持
- ✅ 使用真正的 Clang WebAssembly 编译器
- ✅ 完整的 C++17 标准支持
- ✅ iostream（cin / cout）
- ✅ vector
- ✅ string
- ✅ array
- ✅ algorithm
- ✅ 动态内存
- ✅ 完整的 STL 支持
- ✅ 标准输入（stdin）

### 学习功能
- ✅ 8 个章节的完整教程
- ✅ 每章配有详细讲解和代码示例
- ✅ 章节题库（每章 5 道题）
- ✅ 自动判分和答案解析
- ✅ 错题本功能
- ✅ 学习进度跟踪
- ✅ 代码练习环境

## 部署到 GitHub Pages

### 步骤 1: 创建 GitHub 仓库

1. 在 GitHub 上创建新仓库，命名为 `c-learning`（或其他名称）
2. 设置为公开仓库

### 步骤 2: 上传文件

将以下文件和目录上传到仓库根目录：

```
c-learning/
├── index.html              # 主网站文件
├── .nojekyll              # 告诉 GitHub 不要使用 Jekyll
├── README.md              # 本说明文件
└── clang/                 # C++ 编译器资源文件（必须）
    ├── bin/
    │   ├── clang.wasm.gz
    │   ├── lld.wasm.gz
    │   ├── memfs.wasm.gz
    │   └── sysroot.tar.gz
    └── runtime-manifest.v1.json
```

**重要：** `clang/` 目录包含 C++ 编译器所需的资源文件（约 28 MB），必须完整上传。

### 步骤 3: 启用 GitHub Pages

1. 进入仓库 Settings
2. 找到 Pages 选项
3. Source 选择 "Deploy from a branch"
4. Branch 选择 "main"（或 "master"）/ "root"
5. 点击 Save

### 步骤 4: 访问网站

等待 1-2 分钟后，访问：
```
https://你的用户名.github.io/仓库名/
```

例如：`https://zhangsan.github.io/c-learning/`

## 在 Android 平板上使用

1. 在夸克浏览器中打开 GitHub Pages 链接
2. 网站会自动检测 HTTPS 环境
3. 选择 C 或 C++ 语言
4. 首次使用 C++ 时需要加载编译器（约 20-30 秒）
5. 开始编写和运行代码！

## 技术说明

### C 语言编译器
- 使用纯 JavaScript 实现的解释器
- 完全内嵌在 index.html 中
- 无需外部资源，file:// 和 https:// 都可以使用

### C++ 编译器
- 使用 @live-codes/clang-wasm（Clang 22 WebAssembly 编译器）
- 从 CDN 加载 JS 入口文件
- 编译器资源文件（clang.wasm.gz、lld.wasm.gz 等）需要从网站加载
- 支持完整的 C++17 标准库
- **必须在 HTTPS 环境下使用**
- 首次加载需要下载约 28 MB 的资源文件

## 浏览器兼容性

- ✅ Chrome 70+
- ✅ Firefox 65+
- ✅ Safari 12+
- ✅ Edge 79+
- ✅ 夸克浏览器（Android）

## 注意事项

1. **C++ 必须在 HTTPS 环境下使用**
   - GitHub Pages 自动提供 HTTPS
   - 不能直接使用 file:// 协议打开 index.html

2. **C 语言可以在任何环境下使用**
   - 支持 file:// 协议
   - 支持 https:// 协议

3. **首次加载 C++ 编译器较慢**
   - 需要下载约 20-30MB 的 WASM 文件
   - 后续加载会使用缓存，速度更快

## 测试示例

### C 语言测试

```c
#include <stdio.h>

int main() {
    printf("Hello C!\n");
    return 0;
}
```

### C++ 测试（vector）

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> a;
    a.push_back(10);
    a.push_back(20);
    a.push_back(30);
    
    cout << a[0] << endl;
    cout << a[1] << endl;
    cout << a[2] << endl;
    
    return 0;
}
```

**预期输出：**
```
10
20
30
```

## 许可证

MIT License

## 反馈

如有问题或建议，欢迎提交 Issue。
