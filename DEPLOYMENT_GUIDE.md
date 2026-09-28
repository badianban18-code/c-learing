# GitHub Pages 部署指南

## 📦 文件清单

你需要上传到 GitHub 的文件：

```
c-learning-final/
├── index.html              (216 KB) - 主网站文件
├── .nojekyll               (0 B)    - GitHub Pages 配置文件
├── README.md               (3.4 KB) - 项目说明
└── wasm-compiler/
    └── wasm-compiler.js    (33 KB)  - C 语言解释器
```

**总计：4 个文件**

---

## 🚀 部署步骤

### 步骤 1: 创建 GitHub 仓库

1. 打开 https://github.com/
2. 点击右上角 "+" → "New repository"
3. 填写信息：
   - Repository name: `c-learning`（或其他名称）
   - Description: `C语言学习网站`（可选）
   - 选择 **Public**（公开）
   - **不要** 勾选 "Add a README file"
   - **不要** 勾选 "Add .gitignore"
   - **不要** 勾选 "Choose a license"
4. 点击 "Create repository"

### 步骤 2: 上传文件

**方法 A: 通过网页上传（推荐新手）**

1. 在仓库页面，点击 "uploading an existing file" 链接
2. 将以下文件拖拽到上传区域：
   - `index.html`
   - `.nojekyll`
   - `README.md`
3. 点击 "Add file" → "Create new file"
4. 输入文件名：`wasm-compiler/wasm-compiler.js`
5. 将 `wasm-compiler.js` 的内容粘贴进去
6. 点击 "Commit new file"

**方法 B: 通过 Git 命令行（推荐有经验的用户）**

```bash
# 克隆仓库
git clone https://github.com/你的用户名/c-learning.git
cd c-learning

# 复制文件
cp /path/to/c-learning-final/index.html .
cp /path/to/c-learning-final/.nojekyll .
cp /path/to/c-learning-final/README.md .
mkdir -p wasm-compiler
cp /path/to/c-learning-final/wasm-compiler/wasm-compiler.js wasm-compiler/

# 提交并推送
git add .
git commit -m "Initial commit"
git push origin main
```

### 步骤 3: 启用 GitHub Pages

1. 进入仓库页面
2. 点击 "Settings"（设置）
3. 左侧菜单选择 "Pages"
4. 在 "Source" 部分：
   - Branch: 选择 `main`（或 `master`）
   - 文件夹: 选择 `/ (root)`
5. 点击 "Save"

### 步骤 4: 等待部署完成

- GitHub 会自动部署你的网站
- 通常需要 1-2 分钟
- 刷新 Pages 页面，会看到你的网站链接

### 步骤 5: 访问网站

你的网站地址是：
```
https://你的用户名.github.io/c-learning/
```

例如：
- 用户名: `zhangsan`
- 仓库名: `c-learning`
- 网站地址: `https://zhangsan.github.io/c-learning/`

---

## 📱 在 Android 平板上使用

### 步骤 1: 打开网站

1. 打开夸克浏览器
2. 在地址栏输入你的 GitHub Pages 链接
3. 按回车访问

### 步骤 2: 开始学习

1. 网站首页显示 8 个章节
2. 点击任意章节开始学习
3. 点击 "💻 代码练习" 进入代码编辑器

### 步骤 3: 选择编程语言

在代码练习页面：
- **选择 C**: 立即可以使用，无需加载
- **选择 C++**: 首次需要加载编译器（约 20-30 秒）

### 步骤 4: 编写和运行代码

1. 在代码编辑器中输入代码
2. 如果需要输入，在 "📥 标准输入" 区域填写
3. 点击 "▶️ 运行" 按钮
4. 查看运行结果

---

## ✅ 验证部署成功

### 测试 1: 访问网站

在浏览器中打开你的 GitHub Pages 链接，应该能看到网站首页。

### 测试 2: C 语言测试

1. 进入 "💻 代码练习"
2. 选择 "C" 语言
3. 输入以下代码：

```c
#include <stdio.h>

int main() {
    printf("Hello C!\n");
    return 0;
}
```

4. 点击 "▶️ 运行"
5. 应该看到输出：`Hello C!`

### 测试 3: C++ 测试

1. 选择 "C++" 语言
2. 等待编译器加载（首次需要 20-30 秒）
3. 看到 "● C++就绪" 表示加载成功
4. 输入以下代码：

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

5. 点击 "▶️ 运行"
6. 应该看到输出：
```
10
20
30
```

---

## 🔧 常见问题

### 问题 1: 页面显示 404

**原因:** GitHub Pages 还未部署完成

**解决:** 等待 1-2 分钟后刷新页面

### 问题 2: C++ 编译器加载失败

**原因:** 可能使用了 file:// 协议

**解决:** 确保通过 GitHub Pages 的 HTTPS 链接访问

### 问题 3: 样式显示不正常

**原因:** 可能是缓存问题

**解决:** 清除浏览器缓存或强制刷新（Ctrl+F5）

### 问题 4: 代码无法运行

**原因:** 代码有语法错误

**解决:** 查看错误提示，修正代码

---

## 📊 文件大小说明

| 文件 | 大小 | 说明 |
|------|------|------|
| index.html | 216 KB | 主网站文件（包含所有 CSS 和 JavaScript） |
| wasm-compiler.js | 33 KB | C 语言解释器 |
| README.md | 3.4 KB | 项目说明 |
| .nojekyll | 0 B | GitHub Pages 配置文件 |

**总计:** 约 252 KB

**注意:** C++ 编译器（@live-codes/cpp-wasm）从 CDN 加载，不计入仓库大小。

---

## 🎯 部署检查清单

部署前请确认：

- [ ] 已创建 GitHub 仓库
- [ ] 仓库设置为 Public
- [ ] 已上传所有 4 个文件
- [ ] 文件结构正确（wasm-compiler.js 在 wasm-compiler/ 目录下）
- [ ] 已启用 GitHub Pages
- [ ] 已选择正确的分支和文件夹
- [ ] 等待部署完成（1-2 分钟）
- [ ] 可以访问网站链接
- [ ] C 语言测试通过
- [ ] C++ 测试通过

---

## 📞 获取帮助

如果遇到问题：

1. 检查 GitHub Pages 设置是否正确
2. 查看浏览器控制台错误信息（F12）
3. 确认所有文件都已正确上传
4. 清除浏览器缓存后重试

---

## 🎉 部署完成

恭喜！你的 C 语言学习网站已经部署成功！

现在你可以在任何地方通过浏览器访问和学习 C/C++ 编程了！

**祝你学习愉快！** 🚀
