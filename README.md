This repository demonstrates an issue in stylelint 11.1.1 (see [issue #4388](https://github.com/stylelint/stylelint/issues/4388))

To reproduce do the following:

```
git checkout 11.1.1
npm install
npx stylelint --version
npx stylelint "nobraket/*.css"
npx stylelint "with(braket)/*.css"
```

Notice how the first invocation of stylelint returns linting errors, whereas the second invocation throws a no matches found exception.

```
git checkout 13.7.2
npm install
npx stylelint --version
npx stylelint "nobraket/*.css"
npx stylelint "with(braket)/*.css"
```

Notice how the first invocation of stylelint returns linting errors, whereas the second invocation throws a no matches found exception.


Now compare against 8.3.0

```
git checkout 8.3.0
npm install
npx stylelint --version
npx stylelint "nobraket/*.css"
npx stylelint "with(braket)/*.css"
```

Notice how both invocations of stylelint now return linting errors.
