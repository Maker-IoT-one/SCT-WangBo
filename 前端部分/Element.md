# Element学习

第一个项目

```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8"/>
        <title>碳减排</title>
        <meta name="viewport" content="width=device-width,initial-scale=1.0"/>
        <link rel="stylesheet" href="https://unpkg.com/element-plus/dist/index.css">
        <script src="https://unpkg.com/vue@next"></script>
        <script src="https://unpkg.com/element-plus"></script>
    </head>
    <body>
    <div id="app"></div>

    <script>
        const App = {
            template: `
        <el-row :gutter="20">
          <el-col :span="6"><div class="grid-content ep-bg-purple"><span>Content 1</span></div></el-col>
          <el-col :span="6"><div class="grid-content ep-bg-purple"><span>Content 2</span></div></el-col>
          <el-col :span="6"><div class="grid-content ep-bg-purple"><span>Content 3</span></div></el-col>
          <el-col :span="6"><div class="grid-content ep-bg-purple"><span>Content 4</span></div></el-col>
        </el-row>
      `
        };

        const app = Vue.createApp(App);
        app.use(ElementPlus);
        app.mount("#app");
    </script>

    <style>
        .el-row {
            margin-bottom: 20px;
        }

        .el-row:last-child {
            margin-bottom: 0;
        }

        .el-col {
            border-radius: 4px;
        }

        .grid-content {
            border-radius: 4px;
            min-height: 36px;
        }
    </style>
    </body>
    </html>
```

