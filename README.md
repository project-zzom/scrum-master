## 설치 및 설정 방법
* Ruby 3.2.2-1 버전 다운로드: https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-3.2.2-1/rubyinstaller-devkit-3.2.2-1-x64.exe
* 3 - MSYS2 and MINGW development toolchain 선택

```
gem install bundler
gem install bundle
bundle install
bundle update
bundle exec jekyll serve
```

## 배포 후 공유 미리보기 확인
표지, 설명 문구, 페이지 제목처럼 공유 정보(`og:*`)를 바꿨다면 배포 후 아래 순서로 확인합니다.

1. 배포 결과 확인 (GitHub Pages 반영까지 몇 분 걸릴 수 있음)
   ```
   curl -sL https://zzom.io/scrum-master/about/ | grep -oE '<title>[^<]*</title>|<meta property="og:(title|description|image)"[^>]*>'
   ```
2. 카카오 캐시 초기화: https://developers.kakao.com/tool/debugger/sharing 에서 URL 입력 후 「캐시 초기화」
3. 페이스북 다시 스크랩: https://developers.facebook.com/tools/debug/ 에서 URL 입력 후 「다시 스크랩」
4. 카카오톡 「나에게 보내기」에 링크를 붙여 제목·설명·이미지 확인

### 참고: `_includes/seo.html`
테마 원본을 복사해 `og:title`, `twitter:title`이 「페이지 제목 - 사이트 제목」을 쓰도록 고친 파일입니다. 테마를 업데이트해도 이 파일은 자동으로 따라가지 않으니, 필요하면 새 원본을 받아 같은 두 줄만 다시 고칩니다.

# Minimal Mistakes remote theme starter

Click [**Use this template**](https://github.com/mmistakes/mm-github-pages-starter/generate) button above for the quickest method of getting started with the [Minimal Mistakes Jekyll theme](https://github.com/mmistakes/minimal-mistakes).

Contains basic configuration to get you a site with:

- Sample posts.
- Sample top navigation.
- Sample author sidebar with social links.
- Sample footer links.
- Paginated home page.
- Archive pages for posts grouped by year, category, and tag.
- Sample about page.
- Sample 404 page.
- Site wide search.

Replace sample content with your own and [configure as necessary](https://mmistakes.github.io/minimal-mistakes/docs/configuration/).

---

## Troubleshooting

If you have a question about using Jekyll, start a discussion on the [Jekyll Forum](https://talk.jekyllrb.com/) or [StackOverflow](https://stackoverflow.com/questions/tagged/jekyll). Other resources:

- [Ruby 101](https://jekyllrb.com/docs/ruby-101/)
- [Setting up a Jekyll site with GitHub Pages](https://jekyllrb.com/docs/github-pages/)
- [Configuring GitHub Metadata](https://github.com/jekyll/github-metadata/blob/master/docs/configuration.md#configuration) to work properly when developing locally and avoid `No GitHub API authentication could be found. Some fields may be missing or have incorrect data.` warnings.

## Structure
* https://mmistakes.github.io/minimal-mistakes/docs/structure/

minimal-mistakes
├── _data                      # data files for customizing the theme
|  ├── navigation.yml          # main navigation links
|  └── ui-text.yml             # text used throughout the theme's UI
├── _includes
|  ├── analytics-providers     # snippets for analytics (Google and custom)
|  ├── comments-providers      # snippets for comments
|  ├── footer
|  |  └── custom.html          # custom snippets to add to site footer
|  ├── head
|  |  └── custom.html          # custom snippets to add to site head
|  ├── feature_row             # feature row helper
|  ├── gallery                 # image gallery helper
|  ├── group-by-array          # group by array helper for archives
|  ├── nav_list                # navigation list helper
|  ├── toc                     # table of contents helper
|  └── ...
├── _layouts
|  ├── archive-taxonomy.html   # tag/category archive for Jekyll Archives plugin
|  ├── archive.html            # archive base
|  ├── categories.html         # archive listing posts grouped by category
|  ├── category.html           # archive listing posts grouped by specific category
|  ├── collection.html         # archive listing documents in a specific collection
|  ├── compress.html           # compresses HTML in pure Liquid
|  ├── default.html            # base for all other layouts
|  ├── home.html               # home page
|  ├── posts.html              # archive listing posts grouped by year
|  ├── search.html             # search page
|  ├── single.html             # single document (post/page/etc)
|  ├── tag.html                # archive listing posts grouped by specific tag
|  ├── tags.html               # archive listing posts grouped by tags
|  └── splash.html             # splash page
├── _sass                      # SCSS partials
├── assets
|  ├── css
|  |  └── main.scss            # main stylesheet, loads SCSS partials from _sass
|  ├── images                  # image assets for posts/pages/collections/etc.
|  ├── js
|  |  ├── plugins              # jQuery plugins
|  |  ├── vendor               # vendor scripts
|  |  ├── _main.js             # plugin settings and other scripts to load after jQuery
|  |  └── main.min.js          # optimized and concatenated script file loaded before </body>
├── _config.yml                # site configuration
├── Gemfile                    # gem file dependencies
├── index.html                 # paginated home page showing recent posts
└── package.json               # NPM build scripts
