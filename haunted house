import time
import random
def onebyone(s):
    for word in s:
        print(word, sep='', end = '')
        time.sleep(0.07)
    print()

onebyone("Haunted House")
time.sleep(0.5)
onebyone("프롤로그")
time.sleep(0.5)
onebyone("잠에서 깨어났다.")
onebyone("축축한 느낌이 난다.")
onebyone("이상한 소리가 난다.")
day=0
place='침대'
places=['침대', '거실', '창고', '화장실']
availableplaces=['침대', '거실', '창고', '화장실']
hp=3
inventory=[]
while True:
    day=day+1
    onebyone("오늘은 이 모르는 집에서:")
    time.sleep(0.5)
    onebyone("{}일.".format(day))
    answer=0
    print("당신은 체력은: ", hp)
    time.sleep(1)
    onebyone("당신의 인벤토리:")
    print(inventory)
    time.sleep(1)
        
    print("당신은 지금", place+"에 있습니다.")
    time.sleep(1)
    availableplaces = places.copy()
    availableplaces.remove(place)
                                  
    onebyone("어디에 갈까요?")
    print(availableplaces)
    while answer not in availableplaces:
        answer= input("입력: ")
        if answer not in availableplaces:
            print("선택지 중 하나를 고르시오.")
    
    onebyone("걸어가는중....")
    time.sleep(3)
    if random.choice([1,2,3]) == 1:
        onebyone("당신은 괴물을 만났습니다.")
        onebyone("뛰어!")
        availableplaces.remove(answer)
        print(availableplaces)
        while answer not in availableplaces:
            answer= input("입력: ")
            if answer not in availableplaces:
                print("선택지 중 하나를 고르시오.")
    onebyone("당신은:")
    print(answer+"에 도착했습니다.")
    time.sleep(1)
    place=answer
    if place == "침대":
        #침대-----------------------------------------------------------------------------------------
        onebyone("당신은 자서 체력을 3으로 회복할수 있습니다.")
        onebyone("아니면 당신은 주황 열쇠를 갖고 알려지지 않은 곳으로 갈수 있습니다.")
        while answer != "1" and answer != "2":
            answer = input("1 = 자기  2 = 숨은 방 들어가기. 입력: ")
            if answer != "1" and answer != "2":
                onebyone("선택지 중 하나를 골라주세요.")
        if answer == "2":
            if "주황열쇠" in inventory:
                #숨은방 들어가기
                onebyone("당신은 숨은 방 안으로 들어가기로 결심했습니다.")
                onebyone("핏자국만 보이고 다른건 안 보인다.")
            else:
                onebyone("당신은 주황색 열쇠가 없습니다.")
                onebyone("방에 못 들어갑니다.")
                #자기
                onebyone("당신은 잡니다.")
                print("자는중")
                time.sleep(3)
                if random.choice([1,2]) == 1:
                    onebyone("당신은 괴물을 만났습니다.")
                    hp=hp-1
                    if hp <= 0:
                        onebyone("당신은 죽었습니다.")
                        onebyone("살아남은 일 수:")
                        print(day)
                        time.sleep(5)
                        break
                    else:
                        onebyone("당신의 체력은 -1 되었습니다.")
                else:
                    hp=3
                    onebyone("당신은 체력이 3으로 되었습니다.")


                
        else:
            #자기
            onebyone("당신은 잡니다.")
            print("자는중")
            time.sleep(3)
            if random.choice([1,2]) == 1:
                onebyone("당신은 괴물을 만났습니다.")
                hp=hp-1
                if hp <= 0:
                    onebyone("당신은 죽었습니다.")
                    onebyone("살아남은 일 수:")
                    print(day)
                    time.sleep(5)
                    break
                else:
                    onebyone("당신의 체력은 -1 되었습니다.")
            else:
                hp=3
                onebyone("당신은 체력이 3으로 되었습니다.")
    if place == "창고":
        #창고---------------------------------------------------------------------------------------------------
        onebyone("쓰레기 더미가 보인다.")
        night=0
        while answer != "2":
            onebyone("더 살펴볼까요?")
            answer=0
            while answer != "1" and answer != "2":
                answer = input("1 = 더 살펴보기 2 = 그만 살펴보기 입력: ")
                if night == 1:
                    onebyone("밤이 옵니다.")
                if answer != "1" and answer != "2":
                    onebyone("선택지중 하나를 고르시오.")
                    
            if answer == "1":
                onebyone("살펴보는 중...")
                time.sleep(3)
                if random.choice([1,2,3,4])==1:
                    onebyone("괴물이 나타났습니다!")
                    hp = hp-1
                    if hp<=0:
                        onebyone("당신은 죽었습니다.")
                        onebyone("살아남은 일수:")
                        print(day)
                        time.sleep(5)
                        break
                    else:
                        onebyone("당신의 체력이 -1 되었습니다.")
                else:
                    randomitem=random.choice([1,2,3,4,5])
                    if randomitem==1:
                        onebyone("당신은 주황 열쇠를 찾았습니다. 어디에 사용하는 걸까요?")
                        inventory.append("주황열쇠")
                    if randomitem==2:
                        onebyone("당신은 밴드를 찾았습니다.")
                        if hp<3:
                            hp=hp+1
                        onebyone("체력:")
                        print(hp)
                        time.sleep(1)
                    if randomitem==3:
                        onebyone("당신은 비누를 찾았습니다.")
                        inventory.append("비누")
                    if randomitem==4:
                        onebyone("당신은 밤 토템을 가졌으므로, 밤이 바로 옵니다.")
                        time.sleep(1)
                        night=1
                    if randomitem==5:
                        onebyone("당신은 아무것도 못 찾았습니다.")
    if place == "화장실":
        #화장실----------------------------------------------------------------------------------------------
        onebyone("이상한 소리가 난다.")
        onebyone("당신은 화장실 귀신한테 비누를 줄수도 있고 거울을 살펴볼수 있습니다.")
        while answer != "2" and answer != "1":
            onebyone("1 = 비누 바치기 2 = 거울을 살펴보기.")
            answer = input("입력: ")
            if answer != "2" and answer != "1":
                onebyone("선택지 중에 하나만 고르시오.")
        if answer == "2":
            #거울 보기
            onebyone("당신은 거울을 보기로 결심했습니다.")
            if random.choice([1,2,3,4,5]) == 1:
                #괴물
                onebyone("당신은 괴물을 만났습니다.")
                onebyone("당신의 체력은 -1이 되었습니다.")
                hp=hp-1
                if hp<1:
                    onebyone("당신은 죽었습니다.")
                    onebyone("살아남은 일수:")
                    print(day)
                    time.sleep(5)
                    break
            elif random.choice([1,2]) == 1:
                onebyone("그냥 멀쩡한 거울이였습니다.")
            else:
                onebyone("당신은 배터리를 거울 모서리에서 찾았습니다.")
                inventory.append("배터리")
        if answer == "1":
            #비누 주기
            onebyone("당신은 체력이 +1 되었습니다.")
            hp=hp+1
    if place == "거실":
        #거실--------------------------------------------------------------------------------------------
        onebyone("TV가 보인다.")
        onebyone("금고를 열수 있고, TV를 배터리로 킬수 있다.")
        while answer != "2" and answer != "1":
            onebyone('금고 열기 = 1, TV 키기 = 2')
            answer = input('입력: ')
            if answer != "2" and answer != "1":
                onebyone("선택지 중에 하나만 고르시오.")
        if answer == "1":
            #금고
            onebyone("비밀번호가 필요하다.")
            onebyone("무엇일까?")
            password = input("입력: ")
            if password == "0317":
                randomitem = random.choice([1,2,3])
                if randomitem == 1:
                    onebyone("밴드를 가졌다.")
                    onebyone("+1 체력")
                    if hp<1:
                        hp=hp+1
                if randomitem == 2:
                    onebyone("괴물이다!")
                    hp = hp-1
                    if hp<1:
                        onebyone("당신의 체력은 -1이 되었습니다.")
                    
                    if hp<1:
                        onebyone("당신은 죽었습니다.")
                        onebyone("살아남은 일수:")
                        print(day)
                        time.sleep(5)
                        break
            else:
                #TV
                onebyone("비밀번호를 모르겠다.")
                onebyone("TV를 킬거다.")
                if "배터리" in inventory:
                    onebyone("이상한 소리가 난다.")
                    onebyone("0317. 숫자가 나온다. 이 숫자를 무엇에 쓰어야 하는지 모르겠다.")
                else:
                    onebyone("배터리가 필요하다.")
        else:
            if "배터리" in inventory:
                onebyone("이상한 소리가 난다.")
                onebyone("0317. 이상한 숫자가 나온다. 이 숫자를 무엇에 쓰어야 하는 지 모르갰다.")
            else:
                onebyone("배터리가 필요하다.")
                
        
        
            
            
            
            
            
        

