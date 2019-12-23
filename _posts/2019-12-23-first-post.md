
---
title: "PDL 1_ Perceptron"
date: 2019-12-23 13:00:00 -0400
categories: python deeplearning
---



# PDL 1_ Perceptron

Created: Dec 23, 2019 9:55 AM
Tags: Deep Learning, Python
Updated: Dec 23, 2019 11:29 AM

# Perceptron(퍼셉트론)

---

다수의 신호를 입력 받아서, 하나의 신호를 출력

![PDL%201_%20Perceptron/Untitled.png](PDL%201_%20Perceptron/Untitled.png)

![PDL%201_%20Perceptron/Untitled%201.png](PDL%201_%20Perceptron/Untitled%201.png)

### - And Gate

    def and_gate(x1, x2):
        w1, w2 = 1.0, 1.0  # 가중치
        bias = -1
        y = x1 * w1 + x2 * w2 + bias
        if y > 0:
            return 1
        else:
            return 0

### - Or Gate

    def or_gate(x1, x2):
        w1, w2 = 1.0, 1.0
        b = -0.5
        y = x1 * w1 + x2 * w2 + b
        if y > 0:
            return 1
        else:
            return 0

### - Nand Gate

    def nand_gate(x1, x2):
        w1, w2 = 0.5, 0.5  # 가중치(weight)
        b = 0  # 편향(bias)
        y = x1 * w1 + x2 * w2 + b
        if y < 1:
            return 1
        else:
            return 0

### -  Xor Gate

    XOR(Exclusive OR: 배타적 OR)
    선형 관계식(y = x1 * w1 + x2 * w2 + b) 하나만 이용해서는 만들 수 없음
    NAND, OR, AND를 조합해야 가능

    def xor_gate(x1, x2):
        """XOR(Exclusive OR: 배타적 OR)
        선형 관계식(y = x1 * w1 + x2 * w2 + b) 하나만 이용해서는 만들 수 없음
        NAND, OR, AND를 조합해야 가능
        """
        z1 = nand_gate(x1, x2)
        z2 = or_gate(x1, x2)
        return and_gate(z1, z2)  # forward propagation(순방향 전파)

### - execute

    if __name__== '__main__':
        for x1 in (0, 1):
            for x2 in (0, 1):
                print(f'AND({x1}, {x2}) -> {and_gate(x1, x2)}')
                print(f'NAND({x1}, {x2}) -> {nand_gate(x1, x2)}')
                print(f'OR({x1}, {x2}) -> {or_gate(x1, x2)}')
                print(f'XOR({x1}, {x2}) -> {xor_gate(x1, x2)}')
                print(' ')

### - Result

    C:\dev\lab_dl\venv\Scripts\python.exe C:/dev/lab_dl/ch02/ex01.py
    
    AND(0, 0) -> 0
    NAND(0, 0) -> 1
    OR(0, 0) -> 0
    XOR(0, 0) -> 0
     
    AND(0, 1) -> 0
    NAND(0, 1) -> 1
    OR(0, 1) -> 1
    XOR(0, 1) -> 1
     
    AND(1, 0) -> 0
    NAND(1, 0) -> 1
    OR(1, 0) -> 1
    XOR(1, 0) -> 1
     
    AND(1, 1) -> 1
    NAND(1, 1) -> 0
    OR(1, 1) -> 1
    XOR(1, 1) -> 0
     
    Process finished with exit code 0
