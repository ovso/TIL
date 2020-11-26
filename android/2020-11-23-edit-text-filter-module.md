# EditText에 Filter를 달아보자.

이모지 입력을 제한하거나, 입력 글자수를 제한하는 로직은 자주 쓰인다. 얼마 전에 모듈 형태로 개발해놓았다.

```kotlin
@Suppress("SpellCheckingInspection")
fun EditText.filterEmoji() {
    this.filters = arrayOf(FilterUtil.EMOJI_FILTER)
}

fun EditText.applyFilter(vararg filters: MyInputFilter) {
    val array = Array<InputFilter>(filters.count()) {
        when (val filterType = filters[it]) {
            is MyInputFilter.Emoji -> FilterUtil.EMOJI_FILTER
            is MyInputFilter.MaxLength -> InputFilter.LengthFilter(filterType.length)
        }
    }
    this.filters = array
}

sealed class MyInputFilter {
    object Emoji : MyInputFilter()
    data class MaxLength(val length: Int = 8) : MyInputFilter()
}

```

```java
public class FilterUtil {

    public static InputFilter EMOJI_FILTER = (source, start, end, dest, dstart, dend) -> {
        for (int index = start; index < end; index++) {

            int type = Character.getType(source.charAt(index));

            if (type == Character.SURROGATE || type == Character.OTHER_SYMBOL) {
                return "";
            }
        }
        return null;
    };
}
```

