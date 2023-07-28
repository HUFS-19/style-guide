# HUFS-19 SCSS 스타일 가이드

## Lint

linter는 stlyelint를 사용합니다. 기본 설정은 [stylelint-config-recommended](https://www.npmjs.com/package/stylelint-config-recommended)을 사용합니다.

```jsx
> npm install --save-dev stylelint stylelint-scss stylelint-config-recommended
```

config 설정은 .stylelintrc를 사용합니다.

<br />

### selector

class selector, id selector는 snake_case 또는 kebab-case를 사용합니다.
SCSS 변수명도 마찬가지로 snake_case 또는 kebab-case로 작성합니다.

```SCSS
// bad
.postItem {
  // style
}

// not bad
.post-item {
  // style
}

// good
.post_item {
  // style
}
```

<br />

### nesting

3개 이상 중첩하지 않습니다.
깊은 중첩은 가독성도 좋지않고, 퍼포먼스도 좋지 않으며, 모듈화를 방해 합니다.

```SCSS
// bad
.wrap {
  >.content{
    // style
    >.post-list{
      >.item {
        >.title {
          // style
        }
      }
    }
  }
}

// good
.wrap {
  >.content{
    // style
  }
}

.post-list{
  >.item {
    >.title {
      //style
    }
  }
}
```
