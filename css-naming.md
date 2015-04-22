# CSS 命名

### 基本规则

1. class name 仅用于表示样式, 任何与样式无直接关系的 (e.g. `.homepage`) 不应当使用 class name.
2. 使用 `.ui-*` 表示 component, component 是顶级的模块. (`.ui-button`, `.ui-list`, etc.)
3. `.mod-*` 作为修饰符作用在 component 上. (`.ui-button.mod-primary`, `.ui-title.mod-small`, etc.)
4. `.part-*` 作用在 component 的子元素上. (`.ui-dialog .part-title`, `.ui-searchbar .part-input`, etc.)
5. 使用 `.status-*` 表示状态, 可以作用在任何元素上. (`.ui-dialog.status-show`, `.ui-pager .status-active`, etc.)
6. 使用 `[data-scope]` 区分不同的页面 / 区块, 这部分的命名应该是纯语义化的, 不与样式直接关联的.
  1. 使用 `[data-scope="page-*"]` 区分不同的页面. (e.g. `[data-scope="page-home"]`)
  2. 使用 `[data-scope="section-*"]` 区分不同区块. (e.g. `[data-scope="section-description"]`)
7. 使用 `[data-id]` 在 `[data-scope]` 内进一步的区分元素. (e.g. `[data-scope="section-description"] [data-id="content"]`)

### 附加约束

1. `.status-*` 可以通过 js 添加 / 删除, 而 `.mod-*` 应该为不变的. 不过可以在 css 内建立 `.status-*` 与 `.mod-*` 的对应关系.
2. `.part-*` 在 component 嵌套的时候有可能出现重复, 所以如有必要, 应使用子选择器 (`E > F`) 代替后代选择器 (`E F`).
3. `[data-scop]` 与 `[data-id]` 应设计为 JavaScript 友好的.
