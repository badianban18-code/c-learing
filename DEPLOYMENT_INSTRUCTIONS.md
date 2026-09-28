# 重新部署说明

## 问题原因

之前的 C++ 编译器配置错误：
1. 使用了错误的包名（@live-codes/cpp-wasm 不存在）
2. 没有部署 clang/ 资源文件到 GitHub Pages
3. baseUrl 配置不正确

## 已修复的内容

✅ 使用正确的包：@live-codes/clang-wasm@0.3.0  
✅ 下载了完整的编译器资源文件到 clang/ 目录  
✅ 修正了 baseUrl 配置（使用 `./clang/` 相对路径）  
✅ 修正了编译器 API 调用方式（使用 `compiler.run()`）  

## 需要重新上传的文件

### 1. 更新 index.html
- 文件：`c-learning-final/index.html`
- 大小：216 KB
- 说明：修正了 C++ 编译器加载逻辑

### 2. 新增 clang/ 目录（必须！）
这是 C++ 编译器所需的资源文件，**必须完整上传**：

```
clang/
├── bin/
│   ├── clang.wasm.gz      (15 MB)
│   ├── lld.wasm.gz        (7.5 MB)
│   ├── memfs.wasm.gz      (38 KB)
│   └── sysroot.tar.gz     (5.2 MB)
└── runtime-manifest.v1.json (876 B)
```

**总计：约 28 MB**

### 3. 其他文件（可选）
- `.nojekyll` - 如果之前已上传，不需要重新上传
- `README.md` - 更新了部署说明，建议重新上传

## 部署步骤

### 方法 1：通过 GitHub 网页上传

1. 打开你的 GitHub 仓库：https://github.com/badianban18-code/c-learning
2. 点击 "Add file" → "Upload files"
3. 上传以下文件：
   - `index.html`（覆盖旧文件）
   - `clang/bin/clang.wasm.gz`
   - `clang/bin/lld.wasm.gz`
   - `clang/bin/memfs.wasm.gz`
   - `clang/bin/sysroot.tar.gz`
   - `clang/runtime-manifest.v1.json`
4. 点击 "Commit changes"
5. 等待 GitHub Pages 重新部署（1-2 分钟）

### 方法 2：通过 Git 命令行

```bash
# 克隆仓库
git clone https://github.com/badianban18-code/c-learning.git
cd c-learning

# 复制新文件
cp /path/to/c-learning-final/index.html .
mkdir -p clang/bin
cp /path/to/c-learning-final/clang/bin/* clang/bin/
cp /path/to/c-learning-final/clang/runtime-manifest.v1.json clang/

# 提交并推送
git add .
git commit -m "修复 C++ 编译器配置，添加 clang 资源文件"
git push origin main
```

## 验证部署

### 1. 检查文件是否上传成功

访问以下链接，确认文件可以访问：
- https://badianban18-code.github.io/c-learning/clang/runtime-manifest.v1.json
- https://badianban18-code.github.io/c-learning/clang/bin/clang.wasm.gz

如果能看到 JSON 内容或开始下载文件，说明上传成功。

### 2. 测试 C++ 编译器

1. 打开 https://badianban18-code.github.io/c-learning/
2. 点击"💻 代码练习"
3. 选择"C++"语言
4. 等待编译器加载（首次需要下载 28 MB 资源，可能需要 30-60 秒）
5. 看到"● C++就绪"表示加载成功
6. 输入测试代码：

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

7. 点击"▶️ 运行"
8. 应该看到输出：
```
10
20
30
```

## 常见问题

### Q: C++ 编译器仍然加载失败？

A: 请检查：
1. clang/ 目录是否完整上传（5 个文件）
2. 浏览器控制台是否有错误信息（按 F12 查看）
3. 网络连接是否正常（需要下载 28 MB 资源）
4. 浏览器是否支持 WebAssembly

### Q: 加载速度很慢？

A: 这是正常的，因为需要下载 28 MB 的编译器资源：
- 首次加载：30-60 秒（取决于网络速度）
- 后续加载：会使用浏览器缓存，速度更快

### Q: 可以在 file:// 协议下使用吗？

A: 不可以。C++ 编译器必须在 HTTPS 环境下运行：
- ✅ GitHub Pages（自动 HTTPS）
- ✅ 其他 HTTPS 托管服务
- ❌ file:// 协议
- ❌ http:// 协议

## 技术细节

### C++ 编译器架构

- **包名**: @live-codes/clang-wasm@0.3.0
- **编译器**: Clang 22.1.8（WebAssembly 版本）
- **标准**: C++17（gnu++17）
- **资源文件**:
  - clang.wasm.gz - Clang 编译器核心
  - lld.wasm.gz - 链接器
  - memfs.wasm.gz - 内存文件系统
  - sysroot.tar.gz - C++ 标准库
  - runtime-manifest.v1.json - 运行时配置

### baseUrl 配置

对于 GitHub Pages 项目站点：
```javascript
const baseUrl = new URL('./clang/', window.location.href);
```

这会生成正确的路径：
- 本地：`file:///path/to/c-learning/clang/`
- GitHub Pages：`https://badianban18-code.github.io/c-learning/clang/`

## 文件清单

### 必须上传的文件（5 个）

1. `index.html` (216 KB)
2. `clang/bin/clang.wasm.gz` (15 MB)
3. `clang/bin/lld.wasm.gz` (7.5 MB)
4. `clang/bin/memfs.wasm.gz` (38 KB)
5. `clang/bin/sysroot.tar.gz` (5.2 MB)
6. `clang/runtime-manifest.v1.json` (876 B)

### 可选文件

- `.nojekyll` - 如果之前已上传，不需要重新上传
- `README.md` - 更新了部署说明

## 总结

✅ C 语言：保持不变，立即可用  
✅ C++：需要上传 clang/ 目录（28 MB）  
✅ 首次加载：需要下载 28 MB 资源  
✅ 后续使用：使用浏览器缓存，速度更快  

**部署完成后，C++ 将支持完整的 STL（vector、string、algorithm 等）！**
