# Hugo搭建博客

## 安装步骤

1. 下载[hugo_extended_0.140.2_windows-amd64.zip](https://github.com/gohugoio/hugo/releases/download/v0.140.2/hugo_extended_0.140.2_windows-amd64.zip)，解压得到`Hugo.exe`

2. 将`Hugo.exe`所在目录加入到环境变量

3. 创建新站点。

   ```bash
   hugo new site <name>
   cd <name>
   ```

4. 安装主题`hugo-book`

   ```bash
   git clone https://github.com/alex-shpak/hugo-book.git themes/hugo-book
   ```

5. 修改配置文件`hogo.toml`

   ```toml
   baseURL = '网址'
   languageCode = 'zh'
   title = '站名'
   theme = 'hugo-book'
   
   [params]
         BookTheme = 'dark'
   ```

6. 启动服务

   ```bash
   hugo server
   ```

##  使用说明

- 在`content/docs`下使用`markdown`编写文章

- 目录结构对应了页面里的大纲结构，目录下只有创建`_index.md`才能被大纲识别

- `_index.md`中可以设置目录属性（开头敲`---`回车），正文是目录对应的页面。

**常用属性：**

- `bookFlatSection: true`目录不缩进

- `bookCollapseSection: true`目录收起

- `bookHidden: true`隐藏页面

- `title`目录命名

- `weight`目录排序

## 部署网站

1. 创建Github仓库，将项目同步到仓库

```bash
git init
git add .
git commit -m <message>
git remote add <name> <url>
git push <remote> <local branch>:<remote branch>
```

2. 使用Netlify托管仓库，每次仓库更新，网站会同步更新。

