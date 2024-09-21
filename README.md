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

------------------------------------------
## Transposition Ciphers (전치암호) 

- 전치암호는 한 기호를 다른 기호로 대체시키지 않고, 대신에 그 기호의 위치를 바꾼다.
  >  즉, 전치암호는 기호를 재정렬시킨다.

#1 Keyless Transposition Ciphers
> 과거에 사용된 간단한 전치암호는 키가 없다.

- rail fence ciphers
> 평문은 지그재그패턴으로 두 열에 배열, 암호문은 행 순서의 패턴으로 읽혀져 생성된다.
  <img width="909" alt="스크린샷 2024-09-21 오후 12 41 44" src="https://github.com/user-attachments/assets/a8621fea-c7f1-4137-b263-61dcf4178619">


> - "Meet me at the park" -> "MEMATEAKETETHPR"

- decide the table's the number of columns.
> table의 column 수를 정해두고, 암호화하는 방법. 평문을 Column 수로 계속 나누어 table에 한 row씩 쓴다. 이후, 작성된 table을 column 순서로 읽으면 암호문을 완성할 수 있다.

<img width="530" alt="스크린샷 2024-09-21 오후 1 27 20" src="https://github.com/user-attachments/assets/46f7cb50-1d56-4dcf-afb1-0ccd46ddd6a4">

> - "Meet me at the park" -> "MMTAEEHREAEKTTP" 복호화하는 과정은 Table을 Column순으로 채우면 된다. Column의 수를 미리 정해두었으므로, Ciphertext의 전체길이를 Column 수로 나누어 그 개수만큼 하나의 Column에 쓰고, 작성된 Table을 Row 순서로 읽으면 Plaintext를 완성할 수 있다.


#2 Keyed Transposition Ciphers
> 키가 있는 전치암호
> - _앞서 Keyless Transposition Cipher는 보통 plaintext를 한 row씩 쓰고 한 column씩 읽듯 쓰는 방법과 읽는 방법을 변경해서 ciphertext를 완성시켰다. Keyed Transposition Cipher에서는 이와 달리 Plaintext를 일정한 조각으로 나누어 나누어진 조각을 특정한 규칙에 맞게 글자간 순서를 변경하는 것으로 수행된다. 이때 나눠진 조각을 Block 이라하며, 결국 Plaintext를 Block 단위로 나누어 Block에서 Permutation을 수행하게 되는 것이다.(평문을 나눈 뒤 각각의 블록에 독립적으로 키를 사용하여 문자를 치환하는 것)_

- "Enemy Attacks Tonight" 이라는 문장을 암호화 해보자.
  > - block 크기는 5이고, block의 permutation key(encryption key)는 _**'31452'**_ 라고 가정한다.
  > - block 5개씩 나눴을 때, 한 글자가 부족하므로 plaintext의 마지막에 임의의 알파벳 "z"를 추가한다.
  
<img width="936" alt="스크린샷 2024-09-21 오후 1 47 05" src="https://github.com/user-attachments/assets/2f3a0edb-c730-47ca-a0b2-a96c510cdf6e"><br/>


<img width="225" alt="스크린샷 2024-09-21 오후 1 51 00" src="https://github.com/user-attachments/assets/64a4a00e-623a-4bc2-89e3-e8874d219cb4">

> 이를 해석해보면, 각 Block에서 3번째 글자를 가장먼저 쓰고, 1번째 글자를 두번째로, 4번째 글자를 세번째로 쓰면서 암호화를 진행하라는 말이다. 즉, "enemy" 라는 단어는 "EEMYN"으로 암호화될 것이다. 이 방식으로 전체 문장에 대한 암호화를 진행한 결과는 다음과 같다.

<img width="941" alt="스크린샷 2024-09-21 오후 1 55 05" src="https://github.com/user-attachments/assets/8f3a8c57-a8dd-4b6c-ab0e-9e87e80e3b74">

> Decrypt를 위한 Key의 생성은 위의 표에서 첫 번째 row가 12345 가 되도록 수정한다. Decrypt Key 그림을 통해 설명하면

<img width="223" alt="스크린샷 2024-09-21 오후 2 04 32" src="https://github.com/user-attachments/assets/4ef79eac-10c8-4daa-ae9e-08d1719ea402">

> 2번째 글자가 1번째 글자가 되고, 5번째 글자가 2번째 글자가 되는 방식인 것이다. 이 때 사용한 Decryption Key는 _**'25134'**_ 가 된다. 

<img width="450" alt="image" src="https://github.com/user-attachments/assets/5bf5e339-e848-4115-97e6-4b8cf23eaeb8">

--------------------------

## Combined Transposition Cipher
> 앞선 두 방식을 합쳐서 만들어진 Cipher. (Keyless & Keyed Transposition Cipher)
> - Keyless Transposition Cipher의 Table의 Column을 결정해 Table을 생성한 뒤, Table Column간에 Keyed Transposition Cipher의 Key를 통해서 Permutate 한다. 이후 완성된 Table을 Column by Column 순서로 읽어 Ciphertext를 완성한다.

<img width="542" alt="image" src="https://github.com/user-attachments/assets/1e1d735a-a057-43fa-9d21-5e488ab055bf">

 <img width="222" alt="스크린샷 2024-09-21 오후 2 51 01" src="https://github.com/user-attachments/assets/ab8e5e6b-8ff6-4f60-88f9-54e2f4cc153d">

> 예제로 "ENEMY ATTACKS TONIGHT"를 Encrypt 해보자. 사용되는 key는 마찬가지로 _**'31452'**_ 이며, Block Size는 5이다. Block Size가 5이기 때문에 자동적으로 Column의 수도 5가 된다.
> 우선 plaintext를 column이 5인 table에 채워넣는다. 한글자가 부족하므로 임의의 문자 x(or z)를 추가한다.
> 완성된 기존의 table에서 _**'31452'**_ key를 이용해 column간 순서를 permutate 한다. 이후에 완성된 Table을 Column by Column 순서로 읽으면 된다. 즉, ciphertext는 "ETTAEAKIMAOTYCNXNTSG"가 된다. Decrypt의 경우에는 Column by Column 순서로 Table에 Ciphertext를 채워넣고, Decrption Key _**'25134'**_ 를 이용해 Table의 Column을 Permute한다. 완성된 Table을 Row by Row 로 읽으면 Plaintext를 완성할 수 있다.











