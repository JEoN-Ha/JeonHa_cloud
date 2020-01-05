# 문서를 읽기 전(README)

- 이 문서의 저작권은 '팽대원(FoRA)'에게 있음.
- 중요하다고 생각되는 단어 및 문장은 ***강조 효과***를 달았음.
- 추가적인 설명은 다음과 같이 회색으로 각주 효과를 달았음.

> 각주효과, 각주효과, 각주효과

# Web Scrapping

`requests` package를 import해야 한다.

```python
value = request.get("https://fora22.github.io")
```

`request.get` 함수를 사용하면 해당 URL에 있는 html 정보를 다 가져올 수 있다.

`value.text` 하면 text 정보만, `value.json` 하면 json 정보만, `value.headers` 하면 headers, `value.status_code` 하면 status_code만 필터링 할 수 있다.



## Beautiful Soup

Python library(package)

`pip install beautifulsoup4`를 통해 install 해야 한다.