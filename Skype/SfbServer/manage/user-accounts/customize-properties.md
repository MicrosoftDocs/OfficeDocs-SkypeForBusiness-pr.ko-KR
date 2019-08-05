---
title: 비즈니스용 Skype 서버에 대 한 사용자 계정 속성 사용자 지정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 이 섹션의 절차를 사용 하 여 개별 사용자 계정 속성을 수정할 수 있습니다.
ms.openlocfilehash: fda11a1b52519f3653c841837af20392383cadd1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "36197858"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 사용자 계정 속성 사용자 지정
 
이 섹션의 절차를 사용 하 여 개별 사용자 계정 속성을 수정할 수 있습니다.
  
개별 사용자 수준에서 수행할 수 있는 두 가지 기본 작업은 다음과 같습니다.
  
- [특정 사용자 계정에 대 한 전화 통신 옵션 구성](customize-properties.md#Tel_Op)
    
- [다른 풀로 사용자 이동](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>특정 사용자 계정에 대 한 전화 통신 옵션 구성
<a name="Tel_Op"> </a>

특정 사용자에 대 한 전화 통신 설정을 사용자 지정할 수 있습니다 (비즈니스용 Skype 서버에서 개별 사용자가 사용 하도록 설정 되어 있고 조직이 전화 접속을 지 원하는 경우).
  
비즈니스용 Skype 서버 사용자 전화 통신 옵션은 다음과 같습니다.
  
- **오디오/비디오 사용 안 함** 사용자가 음성 및 영상 통화를 할 수 없습니다.
    
- **Pc 대 pc 전용** 사용자는 pc 대 PC 음성 또는 영상 통화만 할 수 있습니다.
    
- **엔터프라이즈 음성** 사용자는 비즈니스용 Skype 서버 인프라를 사용 하 여 수신 및 발신 전화를 모두 라우팅할 수 있습니다. 사용자는 PC 대 PC 전화도 할 수 있습니다.
    
- **원격 통화 제어** 사용자는 비즈니스용 Skype 서버를 사용 하 여 데스크톱 전화를 제어할 수 있으며 PC 대 PC 통화를 할 수도 있습니다.
    
조직의 전화 통신을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 엔터프라이즈 음성을 사용할 수 있도록 설정](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) 하 고 배포 설명서의 [비즈니스용 Skype 서버에서 enterprise voice 배포](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) 를 참조 하세요.
  
1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.
    
4. **사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 줄의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 찾기를 클릭 합니다. ** **.
    
5. 표에서 수정 하려는 사용자 계정을 클릭 합니다.
    
6. **편집** 메뉴에서 **수정을**클릭 합니다.
    
7. **전화 통신**에서 다음을 수행 합니다.
    
   - 사용자에 게 오디오 및 비디오 통화를 사용 하지 않도록 설정 하려면 **오디오/비디오 사용 안 함을**클릭 합니다.
    
   - 사용자에 대해 PC 대 PC 오디오 통신을 사용 하도록 설정 하 고, 원격 통화 제어 또는 엔터프라이즈 음성을 지원 하지 않으려면 **pc 대 pc 전용**을 클릭 합니다. 사용자가 PC 대 PC 오디오 통신에 사용 하는 전화의 **회선 URI** 값을 지정 합니다.
    
   - Pc 대 PC 오디오 통신을 비롯 한 서비스 정책 수업에 따라 비즈니스용 Skype 인프라를 사용 하 여 사용자의 전화 통화를 라우팅하려면 **엔터프라이즈 음성을**클릭 합니다. **줄 URI**에서 엔터프라이즈 음성의 전화 번호를 지정 합니다. **다이얼 플랜 정책** 및 **음성 정책**에서 사용자에 대 한 적절 한 정책을 지정 합니다. 사용자가 거는 전화 번호를 E 164 형식으로 변환 하기 위한 정규화 규칙을 지정 하려면 **위치 정책**에서 적절 한 위치 프로필을 선택 합니다.
    
   - 사용자가 비즈니스용 Skype 서버에서 데스크톱 전화선을 제어 하 여 pc에서 PC로 거는 통화와 PC에서 전화를 걸 수 있도록 하는 원격 통화 제어 기능을 사용 하도록 설정 하려면 **원격 통화 제어**를 클릭 합니다. **줄 URI**에서 원격 통화 제어에 대 한 전화 번호를 지정 합니다. 사용자에 게는 전화 라우팅에 대해 데스크톱 전화 및 PBX (개인 브랜치 교환) 연결이 있어야 합니다.
    
## <a name="move-users-to-another-pool"></a>다른 풀로 사용자 이동
<a name="Move_Users"> </a>

비즈니스용 Skype Server 제어판을 사용 하 여 특정 서버나 풀에 사용자를 할당할 수 있습니다.
  
> [!TIP]
> Lync Server 2010 이전 버전을 실행 하는 원본 풀의 모든 기존 사용자를 복잡 한 Active Directory 환경의 비즈니스용 Skype 서버 대상 풀에서 이동 하면 Active Directory 복제 속도가 느려질 수 있습니다. 이러한 문제를 방지 하려면 검색 필터를 사용 하 여 Lync Server 2010 이전 버전을 실행 하는 풀에서 사용자를 개별적으로 이동 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자를 cmdlet으로 이동할 수 있습니다. 또한 필터 기능은 비즈니스용 Skype 서버 사용자에 게 작동 합니다. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>선택한 사용자를 다른 서버 또는 풀로 이동 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.
    
4. **사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 줄의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 찾기를 클릭 합니다. ** **. 
    
5. 표에서 특정 사용자 또는 목록에서 사용자를 선택 합니다. 
    
6. **작업** 메뉴에서 **선택한 사용자 이동을 클릭 하 여 그룹으로 이동**합니다.
    
7. **사용자 이동**에서 **대상 등록자 풀**로 사용자를 이동 하려는 풀을 선택 합니다.
    
8. ) 대상 서버 또는 풀을 사용할 수 없는 경우 **강제** 확인란을 선택 합니다.
    
    > [!CAUTION]
    > **강제**를 선택 하면 사용자 계정이 이동 되지만 연결 된 사용자 데이터는 삭제 됩니다 (예: 사용자가 예약한 컨퍼런스). 이를 선택 하지 않으면 계정과 관련 데이터가 모두 이동 합니다. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>한 서버 또는 풀의 모든 사용자를 다른 서버 또는 풀로 이동 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.
    
4. **작업** 메뉴에서 **모든 사용자를 풀로 이동을**클릭 합니다.
    
5. **사용자 이동**에서 **원본 등록자 풀**에서 이동 하려는 사용자 계정이 포함 된 풀을 선택 합니다.
    
6. **대상 등록자 풀**에서 사용자를 이동 하려는 풀을 선택 합니다.
    
7. ) 대상 서버 또는 풀을 사용할 수 없는 경우 **강제** 확인란을 선택 합니다.
    
    > [!CAUTION]
    > **강제**를 선택 하면 사용자 계정이 이동 되지만 연결 된 사용자 데이터는 삭제 됩니다 (예: 사용자가 예약한 컨퍼런스). 이를 선택 하지 않으면 계정과 관련 데이터가 모두 이동 합니다. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>필터를 사용 하 여 한 풀에서 다른 풀로 사용자를 이동 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.
    
4. **사용자 검색**에서 **검색**을 클릭 한 다음 **필터 추가**를 클릭 합니다.
    
5. 검색 조건에서 **등록자 그룹**을 선택 하 고 **같음**, **현재 풀 FQDN**을 차례로 선택한 다음 **찾기를**클릭 합니다.
    
6. **작업** 메뉴에서 **모든 사용자를 풀로 이동을**클릭 합니다.
    
    > [!NOTE]
    > 기존 사용자 집합에 필터가 적용 되는 경우 **모든 사용자를 풀로 이동 하** 는 옵션이 사용자의 필터링 된 하위 집합에 해당 하는 것이 아니라 **** 모든 사용자가 사용할 수 있습니다.
  
7. **사용자 이동**에서 **원본 등록자 풀**에서 이동 하려는 사용자 계정이 포함 된 풀을 선택 합니다.
    
8. **대상 등록자 풀**에서 사용자를 이동 하려는 풀을 선택 합니다.
    
9. ) 대상 서버 또는 풀을 사용할 수 없는 경우 **강제** 확인란을 선택 합니다.
    
    > [!CAUTION]
    > **강제**를 선택 하면 사용자 계정이 이동 되지만 연결 된 사용자 데이터는 삭제 됩니다 (예: 사용자가 예약 하 고 연락처를 사용 하는 컨퍼런스). 이를 선택 하지 않으면 계정과 관련 데이터가 모두 이동 합니다. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Windows Powershell cmdlet을 사용 하 여 한 풀에서 다른 그룹으로 사용자 이동

1. Windows PowerShell 명령 (로컬 또는 원격)을 실행 하는 방법에 따라 다음과 같이 올바른 비즈니스용 Skype 서버 관리 역할의 구성원으로 로그온 해야 합니다.
    
   에서. 로컬 컴퓨터에서 명령을 실행 하는 경우 (예: 프런트 엔드 서버에 직접 로그온 하는 경우) 다음을 수행 합니다. 비즈니스용 Skype 서버 관리 셸이 설치 된 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원으로 로그온 하거나 필요한 경우 **대리인 설정 권한에**설명 된 대로 사용자 권한을 부여 합니다.
    
   b. 다른 컴퓨터에서 원격으로 명령을 실행 하는 경우 (예: 컴퓨터에 로그온 하 고 표준 Edition 프런트 엔드 서버에서 원격으로 명령을 실행 하는 경우) 다음을 수행 합니다. CsUserAdministrator 역할 또는 CsAdministrator에 할당 된 사용자 계정에서 역할을 설정 하 고 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.
    
3. 단일 사용자를 이동 하려면 다음과 같이 Move-CsUser cmdlet을 사용 합니다.
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    이동할 사용자가 사용자 Pilar Ackerman이 고 사용자가 현재 할당 된 홈 풀에서 pool pool01.contoso.net 이동 합니다.
    
4. 많은 수의 사용자를 이동 하려면 **Get-csuser** cmdlet을 사용 하 여 필터를 사용 하 고 사용자의 결과 집합을 **이동-csuser**에 전달 합니다.
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    **Get csuser** 및 **Move csuser** 의 결합 된 명령은 다음과 같이 표시 될 것입니다.
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


