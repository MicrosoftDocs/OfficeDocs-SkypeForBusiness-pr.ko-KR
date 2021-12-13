---
title: 고객에 대한 파트너 관리
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 고객에 대한 파트너 관리.
f1keywords: ''
ms.openlocfilehash: 84d15f43ff49565dbba915470ea618a69ff74ee8
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331237"
---
# <a name="partner-management-for-customers"></a>고객에 대한 파트너 관리


TRM(관리 Teams 룸) 서비스의 파트너 관리를 사용하면 고객이 하나 또는 여러 파트너 조직에 원활하게 액세스 및 책임을 위임할 수 있습니다. 파트너는 관리에 할당된 회의실만 관리할 수 있습니다. 

## <a name="on-boarding-partners"></a>탑승 파트너
   TRM 포털을 통해 파트너를 초대하여 조직과 파트너 조직의 테넌트 간의 관계를 확립합니다. 

### <a name="invitation-to-partner"></a>파트너에 대한 초대

   이 메서드에서 파트너는 사용자에게 할당된 기본 관리자인 사용자의 *UPNS를* 제공해야 합니다. 

**초대를 시작하기 위해** 

1. MMR 관리자로 Teams 룸 관리 포털에 로그인합니다.
1. 파트너 **설정 >** **로** 이동한 다음 파트너 **추가를 선택합니다.**
1. 첫 번째 행에 기본 관리자의 이름과 UPN을 입력합니다.
1. 확인하려면 **연락처 추가를** 선택합니다.
1. 다음 중 하나를 수행합니다.
   - 다른 사용자를 추가하기 위해 4단계를 반복합니다.
   - 사용자를 삭제하려면 사용자의 오른쪽에 있는 bin 아이콘을 선택합니다.

    > [!NOTE]
    > 초대가 UPN에 묶이면 그룹 또는 메일 그룹을 사용할 수 없습니다.

1. 다음을 **선택합니다.**
1. 변경 제어 승인이 필요한 이벤트를 구성합니다. 기본적으로 모든 컨트롤은 자동 **승인으로 설정됩니다.**

   > [!NOTE]
   > *현재 자동 승인만 사용할 수 있습니다.*
   > 
   >  1.  *수동 승인:* 파트너가 작업을 수행하면 고객이 검토하고 승인할 수 있도록 승인 요청이 생성됩니다. 요청이 승인될 때까지 작업이 구현되지 않습니다.
   >  
   >  1. *자동 승인:* 파트너가 작업을 수행하면 승인 요청이 생성되지 않습니다. 작업이 즉시 구현됩니다.
     
1. 다음을 **선택합니다.**
1. 파트너가 관리할 방을 할당한 다음 다음을 **선택합니다.**
1. 계속하려면 약관을 검토하고 **동의를 선택합니다.**
1. 초대의 세부 정보를 검토합니다.
1. 파트너 **추가를 선택하여** 초대를 보낼 수 있습니다.

초대는 각 사용자에 대해 고유하며 독립적입니다. 초대를 수락하는 첫 번째 파트너 사용자는 파트너와 테넌트 간에 연결을 설정합니다. 링크를 설정하는 사용자와 특별한 연결은 없습니다. 사용자가 다시 재할당될 경우 유연성을 허용합니다. 수락할 후속 사용자는 기본 관리자 역할에 자동으로 할당됩니다. 기본 관리자 역할에는 항상 한 사용자 이상이 있어야 합니다.

기본 관리자 역할에서 사용자를 관리하려면 파트너용 [다중 테넌트 관리 를 참조하세요.](multi-tenant-management-partner.md)


## <a name="off-boarding-partners"></a>오프보킹 파트너

**파트너를 제거하려면**

1. MMR 관리자로 TRM-MTM 포털에 로그인합니다.
1. 이동을 설정 > **파트너로 이동합니다.**
1. 제거할 파트너를 선택합니다.
1. 고객 세부 정보 창에서 파트너 **제거를 선택합니다.**
1. **삭제** 를 선택합니다. 
1. 확인 프롬프트에서 사용자와 고객 테넌트 간의 연관을 종료하려면 삭제를 **선택합니다.**

## <a name="managing-partner-roles"></a>파트너 역할 관리

파트너 역할을 사용하면 파트너가 추가 직원에게 책임을 보다 세분화적으로 위임할 수 있습니다. 이러한 역할의 개념은 역할 기반 액세스 제어 에 설명된 [개념과 동일합니다.](microsoft-teams-rooms-premium-rbac.md) 파트너 역할은 사용자 지정 역할과 구분됩니다. 

기본 **관리자 역할은** 추가하는 각 파트너에 대한 유일한 기본 제공 역할입니다. 이 역할에는 TRM 서비스에 대해 해당 파트너가 할당한 회의실에 대한 거의 모든 권한이 [있습니다(표 1 참조).](#table-1) 예를 들어 전 세계에 방이 있는 경우 모든 미국 방을 관리하기 위해 파트너를 할당하는 경우 주 관리자는 해당 회의실에 대한 권한을 관리하고 위임할 수만 있습니다. 이 경우 이 파트너의 기본 관리자는 미국 외부의 모든 회의실에 대한 가시성이 없습니다. 

### <a name="adding-primary-admins-to-partner"></a>파트너에 기본 관리자 추가

이미 파트너에게 초대를 보냈고 해당 관리자에 더 많은 사용자를 추가하려면 파트너 관리자 역할에 추가할 수 있습니다. 이렇게 하여 추가된 사용자에게 초대를 효과적으로 전송합니다.

**기존 파트너에 새 사용자를 추가하는 경우**

1. MMR 관리자로 TRM-MTM 포털에 로그인합니다.
1. 역할 설정 > **로 이동합니다.**
1. 파트너  **역할을 선택합니다.** 
1. 해당 파트너 **이름에** 대한 기본 관리자 역할을 선택합니다.
1. 역할 창에서 할당 **을 선택합니다.**
1. 초대된 **관리자 할당을** 선택합니다. 
1. 초대된 관리자 할당 창에서 구성원 을 **선택합니다.**
1. 편집을 **선택합니다.**
1. 새 사용자의 UPN을 입력하고 연락처 **추가를 선택합니다.**
1. 변경 내용을 확인하려면 저장 을 **선택합니다.**

<!--To remove users for an existing partner~~

1. ~~Login to the TRM-MTM portal as a MMR administrator~~
1. ~~Navigate to **Settings > Roles**~~
1. ~~Select the **Partner roles** tab~~
1. ~~Select the **Primary admin** role for the corresponding Partner name~~
1. ~~In the role pane, select the **Assignments** tab~~
1. ~~Select the **Invited admins** assignment~~ 
1. ~~In the Invited admins assignment pane, select the **Members** tab~~
1. ~~Select the **Edit** icon~~
1. ~~Enter the UPN of the new user and select **Add contact**~~
1. ~~Click **Save** to confirm the changes-->




### <a name="table-1"></a>표 1

|기능|사용 권한|**MMR 관리자**|**사이트 잠재 고객**|**Site Tech**|**파트너 관리자**|
| :- | :- | :- | :- | :- | :- |
|방|보기|||||
||수정|||||
||키 재설정|||||
||키 다운로드|||||
||Unenroll|||||
|그룹 관리|만들기 |||||
||보기|||||
||수정|||||
|링 관리 업데이트|만들기 |||||
||보기|||||
||수정|||||
|보고서|보기|||||
|티켓 관리|고객 인시던트 만들기|||||
||보기|||||
||업데이트|||||
|MMR 설정|보기|||||
||수정|||||
|역할 관리|보기 |||||
||수정|||||





## <a name="security"></a>보안

최종 고객은 데이터에 대한 액세스 권한을 유지하며 파트너를 완전히 제거할 수 있습니다. 

위임된 액세스 기능을 사용하면 파트너는 TRM 서비스 포털 외부에서 다른 권한을 얻지 않습니다. 그러나 다른 Microsoft 제품에서 파생된 TRM 서비스에 있는 모든 데이터는 TRM 서비스의 데이터로 간주됩니다. 예를 들어 통화 품질 보고서는 통화 품질 Teams 데이터에서 파생되는 반면 TRM 포털의 모든 데이터는 사용 권한 범위에 있습니다. 

관리 센터 또는 기타 AAD 또는 Teams 권한이 부여되지 않습니다. 또한 파트너는 초대 범위에 정의되지 않은 회의실을 보거나 수정할 수 있는 액세스 권한이 없습니다. 

데이터는 고객의 테넌트에 상주하며 파트너의 테넌트에 복사되지 않습니다. 

MTM 포털은 Azure AD 인증을 사용하여 파트너의 로그인 자격 증명의 유효성을 검사합니다. 현재 고객의 인증 정책은 파트너에 적용되지 않습니다. 예를 들어 고객이 다단계 인증 정책을 사용하는 경우 파트너로 변환되지 않습니다. 

파트너 활동에 대한 로그를 끌어오기 위해 감사 [를 참조하세요.](multi-tenant-auditing.md) 

> [!NOTE]
> AAD 감사 및 O365 감사는 TRM 포털에서 로그를 캡처하지 않습니다. 