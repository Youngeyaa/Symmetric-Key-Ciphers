# Symmetric-Key-Ciphers / 대칭키 암호화 (InfSec) 


 <img width="617" alt="image" src="https://github.com/user-attachments/assets/2cd16f60-03f2-4032-9a44-b65c4ba5f4ee">

- Alice는 안전하지 않은 채널을 통해, 공격자 Eve가 단순히 채널을 도청해서는 메시지를 이해할 수 없다는 가정 하에, Bob에게 메시지를 보낼 수 있다.
- Alice가 Bob에게 보내는 본래의 메시지를 평문(plaintext)이라하고, 채널을 통해 보내는 메시지를 암호문(ciphertext)이라 한다.
- 평문으로부터 암호문을 생성하기 위해, Alice는 암호 알고리즘(encryption algorithm)과 Bob과 공유된 비밀키를 사용한다.
- 평문을 생성하기 위해, Bob은 복호 알고리즘(decryption algorithm)과 동일한 비밀키를 사용한다.
- 암호,복호 알고리즘을 암호(cipher)라 부르기로 한다.
- 키(key)는 암호가 동작하는데 필요한 값의 집합이다.

<br/>

## P가 평문이라면, C는 암호문이고, K는 키이다.

<img width="577" alt="image" src="https://github.com/user-attachments/assets/9159a218-5762-43ec-9329-d8f1d4cbfb9c">

> 즉, Bop에 의해 생성된 평문 (복호화 결과) P1이 Alice에 의해 작성된 원래의 평문 P와 같음을 증명할 수 있다. 
><img width="558" alt="image" src="https://github.com/user-attachments/assets/8c6a4d6b-91b8-47b9-b440-1c8b8e5df79f">
><img width="558" alt="image" src="https://github.com/user-attachments/assets/47aea8cb-ca18-4236-aac5-011478f4a949">

## Kerckhoff's Principle
- Kerckhoff의 원리에 따라, 공격자 Eve는 항상 암호/복호 알고리즘은 알고 있다고 가정한다.
- 암호의 안전성은 키의 안전성에만 바탕을 둔다.
  > 즉, 키를 알아내기 매우 어려워서 암호/복호 알고리즘을 비공개로 할 필요가 없어야 한다.

<br/>

## Cryptanalysis
<img width="594" alt="image" src="https://github.com/user-attachments/assets/38ae2fb8-57d0-4c08-b8b0-ba89c5b0673f"> <br/>
> 암호분석공격

- 암호문 단독 공격(Ciphertext-Only Attack) <br/>
  <img width="525" alt="image" src="https://github.com/user-attachments/assets/8169f821-8d93-48f3-b6ac-84a19cebacfd"><br/>

  > - 전수조사 공격(Brute-Force Attack)
  > - 통계적인 공격(Statistical Attack)
  > - 패턴 공격(Pattern Attack)
  <br/>

- 알고있는 평문 공격(Known-Plaintext Attack) <br/>
<img width="544" alt="image" src="https://github.com/user-attachments/assets/3f9f7658-427a-4c30-89f3-2bdfddf4bd8b"><br/>

  > "공격자가 암호문을 알고있는 경우."
 <br/>
 
- 선택 평문 공격(Chosen-Plaintext Attack) <br/>
<img width="580" alt="image" src="https://github.com/user-attachments/assets/de1611db-26d1-4499-a16d-3f8ea643695c"><br/>

  > "공격자가 고른 plaintext의 ciphertext를 얻어볼 수 있는 경우." <br/>
  > - 즉, 공격자가 평문을 골라서 암호화할 수 있으며, 예를 들어, 공격자가 "HELLO" 라는 평문을 선택해서 암호화하면, 암호문 "XJCVZ"를 받는 식이다.
<br/>

- 선택 암호문 공격(Chosen-Ciphertext Attack) <br/>
<img width="579" alt="image" src="https://github.com/user-attachments/assets/a2abd3a0-b2b4-4633-9bd4-ea817296065e"> <br/>

  > "공격자가 특정 ciphertext를 선택하여 plaintext로 복호화할 수 있는 경우." <br/>
  > - 즉, 공격자가 암호문을 골라서 복호화할 수 있으며, 예를 들어, 공격자가 "XJCVZ" 라는 암호문을 선택해서 복호화하면, 평문 "HELLO"를 받는 식이다. <br/>
  > - _**선택 평문 공격 보다 강력하다.**_



  








