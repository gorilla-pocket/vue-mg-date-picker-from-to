# vue-mg-date-picker-from-to

## Installation

```
npm i vue-mg-date-picker-from-to
```

## Usage

app.js

```
import DatePickerFromTo from 'vue-mg-date-picker-from-to'
Vue.component('DatePickerFromTo', DatePickerFromTo)
```

Example:

```
<template>
    <section class="container">
        <date-picker-from-to :label="label" :from_dt="from_dt" :to_dt="to_dt"/>
    </section>
</template>

<script>
export default {
    data() {
        return {
            label: 'ラベル',
            from_dt: '',
            to_dt: '',
        }
    },
}
</script>
```

## License

MIT