---
title: 사용자 계정 속성 사용자 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 이 섹션의 절차에 따라 개별 사용자 계정 속성을 수정할 수 있습니다.
ms.openlocfilehash: c2a2f63e31d17e90cea528c3fc8ef88dd1952902
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856655"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>사용자 계정 속성 사용자 비즈니스용 Skype 서버
 
이 섹션의 절차에 따라 개별 사용자 계정 속성을 수정할 수 있습니다.
  
개별 사용자 수준에서는 다음 두 가지 기본 작업을 수행하면 됩니다.
  
- [특정 사용자 계정에 대한 전화 통신 옵션 구성](customize-properties.md#Tel_Op)
    
- [사용자를 다른 풀로 이동](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>특정 사용자 계정에 대한 전화 통신 옵션 구성
<a name="Tel_Op"> </a>

특정 사용자에 대한 전화 통신 설정을 사용자 지정할 수 있습니다(개별 사용자가 전화 통신을 사용하도록 설정되어 비즈니스용 Skype 서버 경우).
  
비즈니스용 Skype 서버 전화 통신 옵션은 다음과 같습니다.
  
- **오디오/비디오 사용 안** 사용자는 오디오 및 비디오로 전화를 걸 수 없습니다.
    
- **PC 대 PC 전용** 사용자는 PC 대 PC 음성 또는 화상 통화만 할 수 있습니다.
    
- **Enterprise Voice** 사용자는 사용자 지정 인프라를 사용하여 비즈니스용 Skype 서버 호출을 모두 라우팅할 수 있습니다. 또한 사용자는 PC 대 PC로 전화를 걸 수 있습니다.
    
- **원격 통화 제어** 사용자는 데스크톱 비즈니스용 Skype 서버 제어하는 데 사용할 수 있으며 PC 대 PC 통화도 할 수 있습니다.
    
조직의 전화 통신 구성에 대한 자세한 내용은 배포 설명서에서 [Enable users for Enterprise Voice in 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) 및 Deploy Enterprise Voice in [비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) 참조하십시오.
  
1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.
    
4. **사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.
    
5. 표에서 수정할 사용자 계정을 클릭합니다.
    
6. **편집** 메뉴에서 **수정** 을 클릭합니다.
    
7. **전화 통신** 에서 다음을 수행합니다.
    
   - 사용자에 대해 음성 및 화상 통화를 사용하지 않도록 설정하려면 **오디오/비디오 사용 안 함** 을 클릭합니다.
    
   - 사용자에 대해 PC 대 PC 음성 통신을 사용하도록 설정하고 원격 통화 제어 또는 Enterprise Voice는 사용하도록 설정하지 않으려면 **PC 대 PC 전용** 을 클릭합니다. 사용자가 PC 대 PC 음성 통신에 사용하는 전화에 대해 **줄 URI** 의 값을 지정합니다.
    
   - PC 대 PC 오디오 통신을 비롯한 서비스 정책 클래스에 따라 비즈니스용 Skype 인프라를 사용하여 사용자의 전화 통화를 **라우팅하려면** 를 Enterprise Voice. **줄 URI** 에서 Enterprise Voice의 전화 번호를 지정합니다. **다이얼 플랜 정책** 및 **음성 정책** 에서 사용자에게 적절한 정책을 지정합니다. 사용자가 건 전화 번호를 E.164 형식으로 변환하는 정규화 규칙을 지정하려면 **위치 정책** 에서 적절한 위치 프로필을 선택합니다.
    
   - 사용자가 PC 대 PC 통화 및 PC 대 전화 통화를 비즈니스용 Skype 서버 데스크톱 전화 줄을 제어할 수 있는 원격 통화 제어를 사용하도록 설정하려면 원격 통화 제어 를 **클릭합니다.** **줄 URI** 에서 원격 통화 제어에 대해 전화 번호를 지정합니다. 사용자에게는 데스크톱 전화가 있어야 하며 통화 라우팅을 위한 PBX(Private Branch Exchange) 연결을 사용할 수 있어야 합니다.
    
## <a name="move-users-to-another-pool"></a>사용자를 다른 풀로 이동
<a name="Move_Users"> </a>

제어판을 비즈니스용 Skype 서버 사용하여 사용자를 특정 서버 또는 풀에 할당할 수 있습니다.
  
> [!TIP]
> Lync Server 2010 이전 버전이 실행되는 원본 풀의 모든 기존 사용자를 복잡한 Active Directory 비즈니스용 Skype 서버 대상 풀로 이동하면 Active Directory 복제 속도가 느려질 수 있습니다. 이러한 문제를 방지하기 위해 검색 필터를 사용하여 Lync Server 2010 또는 이전 버전이 실행되는 풀에서 사용자를 개별적으로 이동하거나 비즈니스용 Skype 서버 관리 셸을 사용하여 cmdlet을 사용하여 사용자를 이동할 수 있습니다. 또한 필터 기능은 사용자와 비즈니스용 Skype 서버 작동합니다. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>선택한 사용자를 다른 서버 또는 풀로 이동

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.
    
4. **사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다. 
    
5. 표에서 목록에서 특정 사용자 또는 사용자를 선택합니다. 
    
6. 작업 **메뉴에서** 선택한 사용자를 **풀로 이동을 클릭합니다.**
    
7. 사용자 **이동에서** 대상 등록자 풀에서 사용자를 이동할 **풀을 선택합니다.**
    
8. (선택 사항) 대상 서버나 풀을 사용할 수 없는 경우 **강제 적용** 확인란을 선택합니다.
    
    > [!CAUTION]
    > **강제 적용** 을 선택하면 사용자 계정이 이동되지만 연결된 사용자 데이터가 삭제됩니다(예: 사용자가 예약한 회의). 이 확인란을 선택하지 않으면 계정 및 연결된 데이터가 둘 다 이동됩니다. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>특정 서버나 풀의 모든 사용자를 다른 서버나 풀로 이동하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.
    
4. **동작** 메뉴에서 **모든 사용자를 풀로 이동** 을 클릭합니다.
    
5. **사용자 이동** 의 **원본 등록자 풀** 에서 이동할 사용자 계정이 있는 풀을 선택합니다.
    
6. **대상 등록자 풀** 에서 사용자를 이동할 풀을 선택합니다.
    
7. (선택 사항) 대상 서버나 풀을 사용할 수 없는 경우 **강제 적용** 확인란을 선택합니다.
    
    > [!CAUTION]
    > **강제 적용** 을 선택하면 사용자 계정이 이동되지만 연결된 사용자 데이터가 삭제됩니다(예: 사용자가 예약한 회의). 이 확인란을 선택하지 않으면 계정 및 연결된 데이터가 둘 다 이동됩니다. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>필터를 사용하여 한 풀에서 다른 풀로 사용자를 이동하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.
    
4. 사용자 **검색에서** **검색을 클릭한** 다음 필터 **추가 를 클릭합니다.**
    
5. 검색 조건에서 **등록자 풀**, **같음**, **현재 풀 FQDN** 을 차례로 선택한 후 **찾기** 를 클릭합니다.
    
6. **동작** 메뉴에서 **모든 사용자를 풀로 이동** 을 클릭합니다.
    
    > [!NOTE]
    > 기존 사용자 집합에 필터가 적용된 경우  모든 사용자를 풀로 이동 옵션은 일부 가능한 사용자가 아니라 필터링된 사용자 하위 집합의 **컨텍스트에** 있습니다.
  
7. **사용자 이동** 의 **원본 등록자 풀** 에서 이동할 사용자 계정이 있는 풀을 선택합니다.
    
8. 대상 **등록자 풀에서** 사용자를 이동할 풀을 선택합니다.
    
9. (선택 사항) 대상 서버나 풀을 사용할 수 없는 경우 **강제 적용** 확인란을 선택합니다.
    
    > [!CAUTION]
    > **강제 적용** 을 선택하면 사용자 계정이 이동되지만 연결된 사용자 데이터가 삭제됩니다(예: 사용자가 예약한 회의 및 대화 상대). 이 확인란을 선택하지 않으면 계정 및 연결된 데이터가 둘 다 이동됩니다. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Powershell cmdlet을 사용하여 한 풀에서 다른 풀로 사용자를 Windows

1. 로컬 또는 원격으로 Windows PowerShell 명령 실행 방법에 따라 다음과 같이 올바른 관리 역할의 구성원으로 비즈니스용 Skype 서버 로그온해야 합니다.
    
   a. 로컬 컴퓨터에서 명령을 실행하는 경우(예: 프런트 엔드 서버에 직접 로그온): 비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치되는 컴퓨터에 로그온하거나 **설치** 권한 위임에 설명된 필요한 사용자 권한으로 로그온합니다.
    
   b. 다른 컴퓨터에서 원격으로 명령을 실행하는 경우(예: 컴퓨터에 로그온하고 Standard Edition 프런트 엔드 서버에서 원격으로 명령을 실행하는 경우): CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 모든 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype 를 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 단일 사용자를 이동하려면 다음과 같이 Move-CsUser cmdlet을 사용합니다.
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    이동할 사용자가 Pilar Ackerman인 위치는 사용자가 현재 할당된 홈 풀에서 현재 할당된 홈 풀로 pool01.contoso.net
    
4. 많은 수의 사용자를 이동하려면 **Get-CsUser** cmdlet과 함께 필터를 사용하고 결과 사용자 집합을 **Move-CsUser** 에 전달합니다.
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    **Get-CsUser** 및 **Move-CsUser** 의 조합 명령의 결과는 다음과 같을 수 있습니다.
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


