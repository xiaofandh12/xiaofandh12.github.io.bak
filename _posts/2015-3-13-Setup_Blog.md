---
layout: default
title: 本博客是如何搭建的
category: 借鉴
comments: true
---

本博客的搭建毫无技术可言，完全是抄袭[minixalpha](http://minixalpha.github.io)的.

# GitHub Pages
参考[GitHub Pages](https://pages.github.com)

1.  Create a new repository: xiaofandh12.github.io
2.  Clone the repository
   
    ```
    git clone https://github.com/xiaofandh12/xiaofandh12.github.io
    ```

3.  Hello World
    
    ```
    cd xiaofandh12.github.io
    echo "Hello World" > index.html
    ```

4.  Push it

    ```
    git add --all
    git commit -m "Initial commit"
    git push -u origin master
    ```

# Use minixalpha.github.io

1. Download [minixalpha.github.io-source.zip](https://github.com/minixalpha/minixalpha.github.io.git)
2. Extract minixalpha.github.io-source.zip => minixalph.github.io-source
3. Copy the files in minixal.github.io-source to xiaofandh12.github.io
4. Delete blog-images/*

    ```
    cd xiaofandh12.github.io/assets/blog-images
    rm -rf *
    ```

5. Modify comments.ext
    
    ```
    cd xiaofandh12.github.io/_includes
    vim comments.ext
    var disqus_shortname = 'minixalpha'; => var disqus_shortname = 'xiaofandh12';
    ```

6. Modify default.html

    ```
    cd xiaofandh12.github.io/_layouts
    vim default.html
    潇湘夜雨 => 游戏人生
    ```

7. Modify gen_archives.rb
    
    ```
    cd xiaofandh12.github.io/_plugins
    vim gen_archives.rb
    deep_merge => merge
    ```
8. Delete all the files in _posts

    ```
    cd xiaofandh12.github.io/_posts
    rm -rf *
    ```

9. Delte all the files in _site

    ```
    cd xiaofandh12.github.io/_site
    rm -rf *
    ```

10. 平常写博客的流程：在_posts/下用Markdown写好博客，保存，退到xiaofandh12.github.io, 然后make即可

以上内容参考自博客[使用 GitHub, Jekyll 打造自己的免费独立博客](http://blog.csdn.net/on_1y/article/details/19259435), GitHub上的[源代码](https://github.com/minixalpha/minixalpha.github.io), 对应的[博客](minixalpha.github.io)

