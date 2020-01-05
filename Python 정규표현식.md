# 문서를 읽기 전(README)

- 이 문서의 저작권은 '팽대원(FoRA)'에게 있음.
- 중요하다고 생각되는 단어 및 문장은 ***강조 효과***를 달았음.
- 추가적인 설명은 다음과 같이 회색으로 각주 효과를 달았음.

> 각주효과, 각주효과, 각주효과

# Python 정규표현식

 문자열 및 문자에는 정규적인 표현식이 있다.

```python
import re

p = re.compile("[0-9]+") # 0~9까지 숫자 반복(+)
m = p.serach("31+49*44")
print(m)
# 결과 [31, 49, 44]
```

문법은 다음과 같다.

- `\d` - 숫자와 매치, [0-9]와 동일한 표현식

- `\D` - 숫자가 아닌 것과 매치, `[^0-9]`와 동일한 표현식이다.
- `\s` - whitespace 문자와 매치, `[ \t\n\r\f\v]`와 동일한 표현식이다. 맨 앞의 빈 칸은 공백문자(space)를 의미한다.
- `\S` - whitespace 문자가 아닌 것과 매치, `[^ \t\n\r\f\v]`와 동일한 표현식이다.
- `\w` - 문자+숫자(alphanumeric)와 매치, `[a-zA-Z0-9_]`와 동일한 표현식이다.
- `\W` - 문자+숫자(alphanumeric)가 아닌 문자와 매치, `[^a-zA-Z0-9_]`와 동일한 표현식이다.

### 반복(+)

 반복을 나타내는 또 다른 메타 문자로 `+`가 있다. `+`는 최소 1번 이상 반복될 때 사용한다. 즉 `*`가 반복 횟수 0부터라면 `+`는 반복 횟수 1부터인 것이다.

### match

```python
import re

p = re.compile("[a-z]+") # 0~9까지 숫자 반복(+)
m = p.match("3 python")
print(m)
# 결과 None
```

 "3 python" 문자열은 처음에 나오는 문자 3이 정규식`[a-z]+'에 부합되지 않으므로 None을 통해 돌려준다.

### search

컴파일된 패턴 객체 p를 가지고 이번에는 search 메서드를 수행해 보자.

```python
>>> m = p.search("python")
>>> print(m)
<_sre.SRE_Match object at 0x01F3FA68>
```

"python" 문자열에 search 메서드를 수행하면 match 메서드를 수행했을 때와 동일하게 매치된다.

```python
>>> m = p.search("3 python")
>>> print(m)
<_sre.SRE_Match object at 0x01F3FA30>
```

"3 python" 문자열의 첫 번째 문자는 "3"이지만 search는 문자열의 처음부터 검색하는 것이 아니라 문자열 전체를 검색하기 때문에 "3 " 이후의 "python" 문자열과 매치된다.

이렇듯 match 메서드와 search 메서드는 문자열의 처음부터 검색할지의 여부에 따라 다르게 사용해야 한다.

### findall

이번에는 findall 메서드를 수행해 보자.

```python
>>> result = p.findall("life is too short")
>>> print(result)
['life', 'is', 'too', 'short']
```

"life is too short" 문자열의 'life', 'is', 'too', 'short' 단어를 각각 `[a-z]+` 정규식과 매치해서 리스트로 돌려준다.

### 실제 해본 결과

```python 
import re

p = re.compile("\W+|\d+")
m = p.findall("31*23/56+4")
print(t)

# 결과 ['31', '*', '24', '/', '56', '+', '4']
```

