
# 第一次构建

主要把文档内容构建出来

```bash
# 构建命令
gradle build
```

- JavaDoc文档结果：`build/docs/javadoc`
- Antora文档结果：`build/site`

## 布局

- 侧边栏：`build/.gradle/nodeproject/ui-bundle/partials/toc.hbs`
- 头内容：`build/.gradle/nodeproject/ui-bundle/partials/header-content.hbs`
- 脚内容：`build/.gradle/nodeproject/ui-bundle/partials/footer-content.hbs`

## 翻译

- 翻译内容目录：`src/docs/antora/modules`

- 翻译提示词：

```
我正在翻译Spring社区的文档，帮我把adoc的文档内容翻译成中文，翻译的时候注意以下几点：

1. 保留adoc的文档格式，输出adoc格式的文档内容
2. 不要删减原文的空格和空行
3. 相关编程专业术语不要翻译
```

## 构建

```yaml
# build/.gradle/nodeproject/antora-playbook.yml，最后添加以下内容
ui:
  bundle:
    url: ./ui-bundle
    snapshot: true
```

```bash
# 构建命令
antora build/.gradle/nodeproject/antora-playbook.yml
```

结果目录：`build/site`

