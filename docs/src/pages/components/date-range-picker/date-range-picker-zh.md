---
title: React Date Range Picker（日期范围选择器）组件
components: DateRangePicker
githubLabel: 'component: DateRangePicker'
packageName: '@material-ui/lab'
materialDesign: https://material.io/components/date-pickers
---

# Date Range Picker [<span role="img" title="Enterprise">⚡️</span>](https://material-ui.com/store/items/material-ui-x/) 日期范围选择器

<p class="description">日期选择器让用户选择一系列的日期。
</p>

> ⚠️ Premium component <br /><br /> The date range picker is intended for Material-UI X, a commercial set of advanced components built on top of the community edition (MIT license) of Material-UI. <br /><br /> This paid extension will include more advanced components (rich data grid, date range picker, tree view drag & drop, etc.). 你现在可以以实惠的价格 [提前使用](https://material-ui.com/store/items/material-ui-x/)。

日期范围选择器让用户选择一个日期范围。

{{"component": "modules/components/ComponentLinkHeader.js"}}

## 要求

该组件依赖于你所使用的日期管理库。 它支持 [date-fns](https://date-fns.org/)，[luxon](https://moment.github.io/luxon/)，[dayjs](https://github.com/iamkun/dayjs)，[moment](https://momentjs.com/) 以及其他任何使用公共 `dateAdapter` 接口的库。

请安装这些库中的任何一个，并使用 `LocalizationProvider` 来包裹到你的 root（或者包裹到该选择器你想要应用的最高位置）来设置正确的日期引擎。

```jsx
// or @material-ui/lab/dateAdapter/{dayjs,luxon,moment} or any valid date-io adapter
import DateFnsAdapter from '@material-ui/lab/AdapterDateFns';
import LocalizationProvider from '@material-ui/lab/LocalizationProvider';

function App() {
  return (
    <LocalizationProvider dateAdapter={DateFnsAdapter}>
      ...
    </LocalizationProvider>
  );
}
```

## 基本用法

请注意，你可以从 [DatePicker]('/api/date-picker/') 中传递几乎任何的属性。

{{"demo": "pages/components/date-range-picker/BasicDateRangePicker.js"}}

## 响应式

日期范围选择器组件是针对运行它的设备进行设计并优化的。

- “手机（Mobile）”版本最适合触控设备和小型屏幕。
- “桌面（Mobile）”版本最适合鼠标设备和大型屏幕。

默认情况下， `DateRangePicker` 组件使用 `@media (pointer: fine)` 媒体查询来确定使用哪个版本。 你也可以使用 `desktopModeMediaQuery` 属性来自定义它。

{{"demo": "pages/components/date-range-picker/ResponsiveDateRangePicker.js"}}

## 不同的月数

请注意，`calendars` 属性仅运行在桌面端。

{{"demo": "pages/components/date-range-picker/CalendarsDateRangePicker.js"}}

## 禁用日期

禁用日期的行为与 `DatePicker` 相同。

{{"demo": "pages/components/date-range-picker/MinMaxDateRangePicker.js"}}

## 自定义输入组件

你可以使用 `renderInput` 属性来渲染自定义的输入。 对于 `DateRangePicker`，它需要**两个**参数 – 分别是开始和结束输入。 如果你需要渲染自定义的输入，请确保将 `ref` 和 `inputProps` 都正确地传入到输入组件中。

{{"demo": "pages/components/date-range-picker/CustomDateRangeInputs.js"}}

## 静态模式

你可以在没有模态框或弹出提示的情况下渲染任何选择器。 为此你需要使用 `StaticDateRangePicker`。

{{"demo": "pages/components/date-range-picker/StaticDateRangePicker.js"}}