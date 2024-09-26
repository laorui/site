---
title: Writing   标题:写
---

{% youtube AIqBubK6ZLc %}

To create a new post or a new page, you can run the following command:创建一个新的帖子或页面，使用如下命令:

```bash   ”“bash
$ hexo new [layout] <title>
```   ' ' '' ' ' ' ' '

`post` is the default `layout`, but you can supply your own. You can change the default layout by editing the `default_layout` setting in `_config.yml`.' post '是默认的' layout '，但你可以提供你自己的。你可以通过编辑' _config.yml '中的' default_layout '设置来改变默认布局。

## Layout   # #布局

There are three default layouts in Hexo: `post`, `page` and `draft`. Files created by each of them is saved to a different path. Newly created posts are saved to the `source/_posts` folder.Hexo中有三种默认布局:“post”，“page”和“draft”。它们各自创建的文件被保存到不同的路径。新创建的帖子被保存到' source/_posts '文件夹。

| Layout  | Path             ||布局|路径|
| ------- | ---------------- |
| `post`  | `source/_posts`  |
| `page`  | `source`         |
| `draft` | `source/_drafts` |

{% note tip Disabling layout %}{% note提示禁用布局%}
If you don't want an article (post/page) to be processed with a theme, set `layout: false` in its front-matter. Refer to [this section](/docs/front-matter#Layout) for more details.如果你不想让一篇文章(帖子/页面)被处理成一个主题，在它的首页设置' layout: false '。请参阅[本节](/docs/front-matter#Layout)了解更多细节。
{% endnote %}

## Filename   # #文件名

By default, Hexo uses the post title as its filename. You can edit the `new_post_name` setting in `_config.yml` to change the default filename. For example, `:year-:month-:day-:title.md` will prefix filenames with the post creation date. You can use the following placeholders:默认情况下，Hexo使用文章标题作为文件名。您可以在' _config '中编辑' new_post_name '设置。Yml '来更改默认文件名。例如:“:年-:月-:日-:标题”。Md '将在文件名前加上创建日期。您可以使用以下占位符:

| Placeholder | Description                                              |占位符|说明|
| ----------- | -------------------------------------------------------- |
| `:title`    | Post title (lower case, with spaces replaced by hyphens) |
| `:year`     | Created year, e.g. `2015`                                |
| `:month`    | Created month (leading zeros), e.g. `04`                 |
| `:i_month`  | Created month (no leading zeros), e.g. `4`               |
| `:day`      | Created day (leading zeros), e.g. `07`                   |
| `:i_day`    | Created day (no leading zeros), e.g. `7`                 |

## Drafts   # #草稿

Previously, we mentioned a special layout in Hexo: `draft`. Posts initialized with this layout are saved to the `source/_drafts` folder. You can use the `publish` command to move drafts to the `source/_posts` folder. `publish` works in a similar way to the `new` command.之前，我们提到了Hexo中的一个特殊布局:“draft”。用这个布局初始化的帖子被保存到' source/_drafts '文件夹中。你可以使用' publish '命令将草稿移动到' source/_posts '文件夹。' publish '的工作方式与' new '命令类似。

```bash   ”“bash   ”“bash
$ hexo publish [layout] <title>
```   ' ' '' ' ' ' ' '

Drafts are not displayed by default. You can add the `--draft` option when running Hexo or enable the `render_drafts` setting in `_config.yml` to render drafts.默认情况下不显示草稿。你可以在运行Hexo时添加'——draft '选项，或者在' _config中启用' render_drafts '设置。Yml '来渲染草稿。

## Scaffolds   # #支架

When creating posts, Hexo will build files based on the corresponding file in `scaffolds` folder. For example:当创建帖子时，Hexo将根据“脚手架”文件夹中相应的文件构建文件。例如:

```bash
$ hexo new photo "My Gallery"
```

When you run this command, Hexo will try to find `photo.md` in the `scaffolds` folder and build the post based on it. The following placeholders are available in scaffolds:

| Placeholder | Description       |
| ----------- | ----------------- |
| `layout`    | Layout            |
| `title`     | Title             |
| `date`      | File created date |

## Supported Formats

Hexo supports posts written in any format, as long as the corresponding renderer plugin is installed.

For example, Hexo has `hexo-renderer-marked` and `hexo-renderer-ejs` installed by default, so you can write your posts in `markdown` or in `ejs`. If you have `hexo-renderer-pug` installed, then you can even write your post in pug template language.

You can rename your posts and change the file extension from `.md` to `.ejs`, then Hexo will use `hexo-renderer-ejs` to render that file, and so do the other formats.
