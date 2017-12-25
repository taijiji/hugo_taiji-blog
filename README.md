# Making Taiji-blog  Hugo
https://taijiji.github.io/taiji-blog/

# make new blog

```
$ hugo new site taiji-blog
```

# Hugo Theme
[Keira](https://themes.gohugo.io/hugo-kiera/)

```
cd themes
git clone --recursive git@github.com:avianto/hugo-kiera.git
```

# edit config.toml

```
$ vi config.toml

baseURL = "https://taijiji.github.io/taiji-blog/"
languageCode = "en-us"
title = "taiji-blog"
theme = "hugo-kiera"
canonifyurls = true
publishdir = "public"
```

# Post blog

```
$ hugo new post/20171217.md

/Users/taiji/work/hugo_taiji-blog/content/post/20171217.md created
```

edit blog 

```
vi content/post/20171217.md
```

```
---
title: "20171217"
date: 2017-12-17T18:45:04-08:00
draft: true
---

# sample blog
print(Hello Hugo!)
```

# preview
```
cd taiji-blog
hugo server -t hugo-kiera --watch
```

web browse
http://localhost:1313/taiji-blog/

# hosting on Github pages

```
$ hugo 
```

```
$ cd public/
$ git init
$ git remote add origin git@github.com:taijiji/taiji-blog.git
$ git checkout -b gh-pages
$ git add --all
$ git commit -m'initial commit for gh-pages'
$ git push origin gh-pages
```

```
$ vi .gitignore

themes
public
*.swp
```

```
$ cd ..
$ git remote add origin git@github.com:taijiji/taiji-blog.git
$ git add .gitignore config.toml 
$ git commit -m'initial commit'
$ git push origin master
```



# Reference
- [HugoとGitHub Pagesで静的サイトを公開する](https://qiita.com/satzz/items/e24bd703fc04fb45f7ef)
    - gh-pages ブランチを切る方法を採用
- [Hugo + Github Pagesでブログを公開してみた](https://qiita.com/eichann/items/4fe61b8b9bbafcfbe847)
    - レポジトリー2つ用意する形は煩雑なので、最終的に利用せず
- [HUGO: Host on GitHub](http://gohugo.io/hosting-and-deployment/hosting-on-github/)
    - git push upstream gh-pages などの一部使えないコマンドが記載されているので要注意。HugoとGitHub Pagesで静的サイトを公開するのほうが現実的。