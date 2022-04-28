# MIDTERM
---------------------------------------------
# Ford-Fulkerson Algorithm
## Ford-Fulkerson Algorithm이란?
Ford-Fulkerson 알고리즘은 네트워크 또는 그래프에서 가능한 최대 흐름을 계산하기 위한 접근방식입니다.
### flow network
flow network라는 용어는 source(S)와 sink(T)가 있는 꼭짓점과 가장자리의 네트워크를 설명하는 데 사용됩니다. S와 T를 제외한 각 꼭짓점은 그것을 통해 같은 양의 물건을 받고 보낼 수 있습니다. S는 보내기만 가능하고 T는 받기만 가능합니다.
![image](https://user-images.githubusercontent.com/101376842/165790796-98564c14-5dac-4a84-832e-08184c25b177.png)
## Ford-Fulkerson Algorithm의 작동방법
1. 모든 모서리의 흐름을 0으로 초기화합니다.
2. 소스와 싱크 사이에 증가 경로가 있는 동안 이 경로를 흐름에 추가합니다.
3. 잔차 그래프를 업데이트 합니다.
( 필요한 경우 역경로를 고려할 수도 있습니다. 고려하지 않으면 최대 흐름을 찾을 수 없기 때문입니다.)
* 증강 경로 - flow network에서 사용할 수 있는 경로입니다.
* 잔차 그래프 - 추가 가능한 흐름이 있는 flow network를 나타냅니다.
* 잔여 용량 - 최대 용량에서 유량을 뺀 엣지의 용량입니다.

## Ford-Fulkerson의 예
모든 모서리의 흐름은 처음에 0입니다.
![image](https://user-images.githubusercontent.com/101376842/165792680-057aae26-1d68-4fef-b39a-8dfae10c6a29.png)
1.S에서 T까지 임의의 경로를 선택합니다. (S-A-B-T선택)
![image](https://user-images.githubusercontent.com/101376842/165792808-4215b722-156f-4c03-ad74-073641e75d68.png)
세 모서리 중 최소 용량은 2(B-T). 이를 바탕으로 flow/capacity(흐름/용량)을 각 경로에 대해서 업데이트합니다.
![image](https://user-images.githubusercontent.com/101376842/165793138-b50095e8-3ee7-412b-bd24-3d4549fa84e5.png)


2. 다른 경로를 선택합니다(S-D-C-T). 이 모서리 중 최소 용량은 3(S-D)입니다.
![image](https://user-images.githubusercontent.com/101376842/165793731-8fa67adb-727d-432b-bf06-6f8f0a913dfb.png)
이에 따라 용량을 업데이트합니다.
![image](https://user-images.githubusercontent.com/101376842/165793774-4bb07d6b-c782-430d-9b60-47432a8b63ae.png)

3. 이제 역경로 (B-D)도 생각해봅시다. 경로 (S-A-B-D-C-T)를 선택합니다. 가장자리 중 최소 잔존 용량은 1(D-C)입니다.
![image](https://user-images.githubusercontent.com/101376842/165794122-d93029cd-904d-4f1c-93b4-1a59574d2d80.png)
용량을 업데이트합니다.
![image](https://user-images.githubusercontent.com/101376842/165794189-9fd75867-0d12-4d38-a5eb-a2289c710376.png)
순방향 및 역방향 경로에 대한 용량은 별도로 고려됩니다.

4. 모든 흐름을 더하면 2+3+1=6이고, 이는 flow network에서 가능한 최대 흐름입니다.
* edge의 용량이 가득 차면 해당 경로를 사용할 수 없습니다.








