# 문서를 읽기 전(README)

- 이 문서의 저작권은 '팽대원(FoRA)'에게 있음.
- 중요하다고 생각되는 단어 및 문장은 ***강조 효과***를 달았음.
- 추가적인 설명은 다음과 같이 회색으로 각주 효과를 달았음.

> 각주효과, 각주효과, 각주효과

# Python calculator

### 후위표기법(postfix_notation)

> 컴퓨터 프로그램에서 계산하기 쉽게 연산 기호를 피연산자 보다 뒤에 표기하는 것을 후위표기법이라 부른다.

2 + 3 * 5 -> 2 3 5 * +

이렇게 후위 표기한 것을 피연산자는 스택에 보관하고 피연산자는 스택에 보관한 두 개의 피연산자를 꺼내와서 계산한 후, 스택에 보관하면 맨 마지막에 스택에 남아있는 값이 수식의 연산 결과이다.



### 후위표기법 변환(Postfix change)

```python
def change_postfix(self, mathmatical_expression):
        for m_e in mathmatical_expression:
            if self.is_number(m_e):
                self.postfix_notation.append(m_e)
            elif m_e in self.operator:
                prime_number = self.priority_judge(m_e)
                while len(self.stack) > 0:
                    top_of_stack = self.stack[-1]
                    if self.priority_judge(top_of_stack) < prime_number:  
                        break
                    while len(self.stack) > 0:
                        self.postfix_notation.append(self.stack.pop())
                self.stack.append(m_e)
            elif m_e == "(":
                self.stack.append(m_e)
            elif m_e == ")":
                while True:
                    temp = self.stack.pop()
                    if temp == "(":
                        break
                    self.postfix_notation.append(temp)

        while len(self.stack) > 0:
            self.postfix_notation.append(self.stack.pop())
```

`self.stack`과 `self.postfix_notation`으로 구성되어 후위 표기법으로 변환한다.

`*, /`가 우선순위가 가장 높고,  `+, -`가 다음으로 높다. `(`는 우선순위가 가장 낮다. 연산자 중 `)`을 만나면 `(`를 만날때까지 `self.stack`에 있는 것들을 `self.postfix_notation`으로 빼낸다.



### 후위표기법 연산

```python
def calc_data(self):
        for op in self.postfix_notation:
            if self.is_number(op):
                self.stack.append(op)
            elif op in self.operator:
                y_stack = self.stack.pop()
                x_stack = self.stack.pop()
                temp = self.operation(x_stack, y_stack, op)
                self.stack.append(temp)
        if len(self.mathmatical_expression) == 0:
            print("수식을 잘못 입력하셨습니다.")
            print(" ")
        else:
            print(self.stack[0])
            print(" ")
```

피연산자(숫자)이면 `self.stack`에 넣고, 연산자이면 `self.stack`에서 피연산자 2개를 꺼내어 연산을 실행한다.