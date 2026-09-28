# 🚀 快速开始指南

## 你需要上传的文件（共4个）

```
c-learning-final/
├── index.html              (216 KB)  ← 必须上传
├── .nojekyll               (0 B)     ← 必须上传
├── README.md               (3.4 KB)  ← 建议上传
└── DEPLOYMENT_GUIDE.md     (5.7 KB)  ← 可选上传
```

## 部署步骤（5分钟完成）

### 第1步：创建GitHub仓库

1. 打开 https://github.com/
2. 点击右上角 "+" → "New repository"
3. 填写：
   - Repository name: `c-learning`
   - 选择 **Public**
   - **不要**勾选任何初始化选项
4. 点击 "Create repository"

### 第2步：上传文件

1. 在仓库页面，点击 "uploading an existing file"
2. 将以下4个文件拖拽到上传区域：
   - `c-learning-final/index.html`
   - `c-learning-final/.nojekyll`
   - `c-learning-final/README.md`
   - `c-learning-final/DEPLOYMENT_GUIDE.md`
3. 点击 "Commit changes"

### 第3步：启用GitHub Pages

1. 进入仓库 **Settings**
2. 左侧菜单选择 **Pages**
3. Source 部分：
   - Branch: 选择 `main`
   - Folder: 选择 `/ (root)`
4. 点击 **Save**

### 第4步：等待部署

- 等待1-2分钟
- 刷新页面，会看到网站链接：
  ```
  https://你的用户名.github.io/c-learning/
  ```

### 第5步：访问网站

在夸克浏览器中打开链接，即可开始学习！

---

## 在Android平板上使用

### 1. 打开网站
- 在夸克浏览器中输入GitHub Pages链接
- 例如：`https://zhangsan.github.io/c-learning/`

### 2. 选择编程语言
- **C语言**: 立即可用
- **C++**: 首次需要加载20-30秒

### 3. 开始学习
- 点击章节开始学习
- 点击"💻 代码练习"编写代码
- 点击"▶️ 运行"查看结果

---

## 测试代码

### C语言测试

```c
#include <stdio.h>

int main() {
    printf("Hello C!\n");
    return 0;
}
```

### C++测试（vector）

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

---

## 常见问题

**Q: C++编译器加载失败？**
A: 确保通过HTTPS访问（GitHub Pages自动提供HTTPS）

**Q: 页面显示404？**
A: 等待1-2分钟后刷新，或检查Pages设置

**Q: 代码无法运行？**
A: 检查代码语法，查看错误提示

---

## 文件说明

| 文件 | 大小 | 作用 | 是否必须 |
|------|------|------|----------|
| index.html | 216 KB | 主网站文件 | ✅ 必须 |
| .nojekyll | 0 B | GitHub Pages配置 | ✅ 必须 |
| README.md | 3.4 KB | 项目说明 | ✅ 建议 |
| DEPLOYMENT_GUIDE.md | 5.7 KB | 部署指南 | ⭕ 可选 |

---

## 技术支持

- C语言：纯JavaScript解释器，内嵌在index.html中
- C++：Clang WebAssembly编译器，从CDN动态加载
- 数据存储：浏览器localStorage
- 兼容性：Chrome 70+, Firefox 65+, Safari 12+, 夸克浏览器

---

**祝你学习愉快！** 🎉
