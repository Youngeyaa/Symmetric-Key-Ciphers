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
