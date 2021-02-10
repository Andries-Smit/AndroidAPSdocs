# 프로파일 변경

AndroidAPS를 시작하고 프로파일을 선택할 때 사용자는 zero duration(뒤에 설명됨) 으로 "프로파일 변경"이라는 메뉴를 사용할 것이다. AAPS는 프로파일의 이력을 추적할 수 있고 사용자가 매번 새로운 프로파일을 변경하면 NS에 "프로파일 변경"을 요청한다. 업데이트된 프로파일은 즉시 AAPS에 전달되지만 사용자는 NS나 AAPS에서 같은 프로파일로 교체해야 한다.

내부적으로 AAPS는 시작 날짜와 지속 시간으로 프로파일 스냅샵을 생성고 선택된 기간내에서 사용한다. Duration of zero는 기간이 없음을 의미한다. 그러한 프로파일은 새로운 "프로파일 변경"을 할 때까지 유효하다.

To do a profile switch long-press on the name of your profile ("Tuned 03/11" in the picture below).

![프로파일 변경하기](../images/ProfileSwitch_HowTo.png)

만약 사용자가 지속 시간이 있는 "프로파일 변경"을 사용했다면 지속 시간이 지난 후에 이전에 유효했던 프로파일로 다시 돌아가게 된다.

만약 사용자가 AAPS 내부에 있는 프로파일 변경 메뉴를 이용한다면 해당 메뉴에서 버튼을 눌러야 한다.(그것은 "프로파일 변경"으로 동작한다.)

"프로파일 변경" 메뉴 내에서 사용자가 프로파일 비율을 변경하게 되면 두가지 추가적인 변화를 선택할 수 있다.

## 비율

* 이것은 모든 파라미터들을 같은 비율로 적용한다. 
* 만약 사용자가 비율을 130%(인슐린이 30% 더 추가됨을 의미) 로 설정했다면 그것은 30%만큼 basal 양을 증가 시킬 것이다. 따라서 더 낮은 ISF나 IC가 적용될 것이다.
  
  ![프로파일 비율 변경의 예](../images/ProfileSwitchPercentage.png)

* 그리고 그것이 기본 basal양으로 펌프에 전달될 것이다.

* Loop 알고리즘(Open 또는 Closed) 은 선택된 프로파일 비율로 동작할 것이다. 그래서 예를 들어 분리된 프로파일 비율은 호르몬 주기에 따라 다르게 설될 수 있다.

## 시간 이동

![프로파일 비율 변경과 시간 이동](../images/ProfileSwitchTimeShift2.png)

* 이것은 입력된 시간 만큼 시계를 이동시킨다. 
* 그래서 예를 들어, 밤 교대 근무를 할 때 자는 시간이나 깨는 시간을 얼마나 늦게/일찍게 할지 결정합니다.
* 이것은 시간 단위의 프로파일 설정이 현재 시간으로 설정되어 있기 때문에 그부분이 교체 된다는 것이다. 이 시간은 시간 단위로 이동되어야 합니다. 그래서 다음 예제에서 설명하는 방향을 이해해야 한다. 
  * 현재 시간: 12:00
  * **Positive:** 시간 이동 
    * 2:00 **+10 h** -> 12:00
    * 2:00에서의 설정은 positive 시간 이동을 했기 때문에 12시에 사용 될 것이다.
  * **Negative** 시간 이동 
    * 22:00 **-10 h** -> 12:00
    * 22:00 (오후 10시)에서의 설정은 negative 시간이동을 했기 때문에 12:00시에 사용될 것이다.

![프로파일 변경 시간 시간 이동 안내](../images/ProfileSwitch_PlusMinus2.png)

프로파일의 스냅샷을 이용하는 이런 메카니즘은 과거 보다 더 정확한 계산과 프로파일 변경 을 추적할 수 있게 해준다.

## 프로파일 에러 해결하기

### '유효하지 않은 프로파일'/'Basal 프로파일이 시간 단위로 세팅되지 않았다.'

![Basal은 시간단위로 설정되지 않았다.](../images/BasalNotAlignedToHours2.png)

* 이러한 에러 메시지는 만약 사용자가 basal 양이나 I:C 비율을 시간단위로 설정하지 않았을 경우 발생할 것이다. (예를 들어 DanaR과 DanaRS 펌프는 30분 단위의 변경을 지원하지 않는다.)
  
  ![예시된 프로파일은 시간단위로 설정되지 않았다.](../images/ProfileNotAlignedToHours.png)

* 에러 메세지 아래에 날짜와 시간(위에 스크린샷에서는 26/07/2019 5:45)을 확인해야 한다.

* 관리 탭으로 이동
* '프로파일변경'을 선택
* 에러 메세지에서 확인한 시간과 날짜를 찾을 때까지 스크롤.
* 삭제 메뉴로 이용
* 가끔씩 문제가 있는 프로파일 변경이 없을 수도 있다. 이런 경우에는 다른것들도 삭제한다.
  
  ![프로파일 변경 삭제](../images/PSRemove.png)

아래에 설명된 대로 mLab의 프로파일 변경에서 직접 삭제할 수도 있다.

### 'NS에서 프로파일 변경을 수신했지만 폰에는 존재하지 않는다'

* 요청된 프로파일은 Nightscout에서 올바르게 동기화 되지 않았다.
* 프로파일 변경을 삭제하기 위해서 위의 안내에 따라야 한다.

mLab의 프로파일 변경에서 직접 삭제할 수도 있다.

* mlab collection으로 이동
* 프로파일 변경을 위해 treatments를 선택
* 에러 메시지에서 언급된 날짜와 시간의 프로파일 변경을 삭제 ![mlab](../images/mLabDeletePS.png)

### 'DIA, 3시간은 너무 짧다.'

* 프로파일에서 인슐린 작용 시간이 적절하지 못하다면 AndroidAPS는 정확히 동작하지 않고 이러한 에러 메시지를 보여준다. 
* Read about [selecting the right DIA](https://www.diabettech.com/insulin/why-we-are-regularly-wrong-in-the-duration-of-insulin-action-dia-times-we-use-and-why-it-matters/), and edit it in your profile then do a [Profile Switch](../Usage/Profiles) to continue.