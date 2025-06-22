# `variables.css` 变量说明文档

## 概述

`variables.css` 文件集中管理了项目中使用的所有设计变量，这些变量来源于 Figma 设计稿，并转换为 CSS 自定义属性（CSS Custom Properties）。通过使用这些变量，可以确保项目样式的一致性，提高代码的可维护性和主题切换的灵活性。

## 文件内容

该文件包含以下主要类型的变量：

- **颜色 (Colors)**：包括品牌色、功能色（如青蓝色、蓝紫色、暖红色等）、背景色和特定功能色（如成功、警告等）。
- **半透明 (Translucency)**：包括不同透明度下的灰色、品牌色和白色。
- **渐变 (Gradients)**：Figma 数据中为空，可能需要手动补充或在其他地方定义。
- **边框圆角 (Border Radii)**：定义了不同大小的圆角值。
- **字号 (Font Sizes)**：定义了文本的不同字号。
- **字体 (Font Families)**：定义了项目使用的字体族。
- **行高 (Line Heights)**：定义了文本的不同行高。
- **字重 (Font Weights)**：定义了文本的不同字重。
- **文字颜色 (Text Colors)**：定义了不同层级的文字颜色。
- **复合字体样式 (Composite Font Styles)**：结合了字体、字重、字号和行高的复合样式，分为通用文本和价格文本。

## 变量命名规范

变量命名遵循以下模式，以便清晰地表达其用途和来源：

`--[类型]-[子类型]-[具体描述]: [值];`

- **类型**: `color` (颜色), `transparency` (半透明), `bg` (背景色), `gradient` (渐变), `border-radius` (边框圆角), `font-size` (字号), `font-family` (字体), `line-height` (行高), `font-weight` (字重), `font` (复合字体样式)。
- **子类型**: 进一步细分类型，如 `brand` (品牌色), `gray` (灰色), `cyan-blue` (青蓝色), `text` (文字), `price` (价格) 等。
- **具体描述**: 详细说明变量的用途或具体值，如 `5` (色阶), `primary` (主要), `1-4` (4%透明度), `12` (字号12px), `medium` (中等字重)。

**示例:**

- `--color-brand-5`: 品牌色，色阶5
- `--transparency-gray-1-4`: 灰色，4%透明度
- `--bg-white`: 白色背景色
- `--border-radius-8`: 8像素的边框圆角
- `--font-size-16`: 16像素的字号
- `--font-family-pingfang-sc`: 苹方字体
- `--line-height-20`: 20像素的行高
- `--font-weight-medium`: 中等字重
- `--font-secondary-text-emphasis-12m`: 次要文字强调，12号中等字重，16行高

## 如何使用

在您的 CSS 文件中，您可以通过 `var()` 函数来引用这些自定义属性。例如：

```css
.my-component {
  background-color: var(--bg-global-gray);
  color: var(--color-text-primary);
  font-size: var(--font-size-14);
  line-height: var(--line-height-18);
  border-radius: var(--border-radius-4);
}

.my-button {
  background-color: var(--color-brand-5);
  color: var(--color-white);
  padding: 10px 20px;
  border-radius: var(--border-radius-6);
  font-weight: var(--font-weight-semibold);
}

.price-display {
  font: var(--font-price-24);
  color: var(--color-gold-5);
}
```

## 维护与更新

- 当 Figma 设计稿中的变量发生变化时，应及时更新 `variables.css` 文件。
- 避免直接在组件样式中硬编码颜色、字体等值，而应优先使用 `variables.css` 中定义的变量。
- 对于 Figma 中为空的渐变变量，如果后续有明确的定义，请手动添加到 `variables.css` 并更新此文档。

这份文档将帮助团队成员理解和使用项目中的设计变量，确保开发过程中的一致性。 