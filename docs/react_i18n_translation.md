# React i18n translation

## Basic usage

```javascript
import { useTranslation } from 'react-i18next';

function Component() {
  const { t } = useTranslation();
  return (
    <h1>{t("title")}</h1>
  )
}
```

## Set up

[i18n quick start doc](https://react.i18next.com/latest/using-with-hooks)
