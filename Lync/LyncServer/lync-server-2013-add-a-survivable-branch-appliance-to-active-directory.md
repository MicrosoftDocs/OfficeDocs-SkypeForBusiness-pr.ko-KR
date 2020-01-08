---
title: 'Lync Server 2013: Active Directory에 SBA(Survivable Branch Appliance) 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc057318a0d241a28b8529802ea9f2016a1f5b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Lync Server 2013에서 Active Directory에 SBA(Survivable Branch Appliance) 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-23_

Survivable Branch 기기를 배포 하려는 경우 Active Directory 도메인 서비스에 Survivable Branch 기기를 추가 해야 합니다. 중앙 사이트에서이 절차를 수행 합니다.

<div>


> [!IMPORTANT]  
> Survivable Branch 기기를 배포 하는 경우에만이 절차를 수행 합니다. Survivable Branch 서버를 배포 하는 경우에는이 작업을 수행 하지 마십시오.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>Active Directory 도메인 서비스에 Survivable Branch 기기를 추가 하려면

1.  엔터프라이즈 관리자 그룹의 구성원으로 구성원 서버에 로그온 합니다.

2.  **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **Active Directory 사용자 및 컴퓨터**를 클릭 합니다.

3.  **작업** 메뉴에서 **새로 만들기** 를 클릭 한 다음 **컴퓨터**를 클릭 합니다.

4.  **새 개체-컴퓨터** 대화 상자에서 Survivable Branch 기기 컴퓨터 개체의 이름 (예: BranchOffice1)을 입력 하 고 **변경을**클릭 합니다.

5.  **사용자 또는 그룹 선택** 대화 상자에서 RTCUniversalSBATechnicians 그룹을 추가 하 고 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 지점 사이트에서 RTCUniversalSBATechnicians 그룹의 구성원은 나중에이 장치를 도메인에 추가 합니다.

    
    </div>

6.  **확인** 을 클릭 하 여 Survivable Branch 기기 컴퓨터 개체를 저장 합니다.

7.  **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **ADSI 편집**을 클릭 합니다.

8.  **ADSI 편집**에서 이전 단계에서 만든 컴퓨터 개체를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

9.  특성 목록에서 **servicePrincipalName**를 클릭 한 다음 **편집**을 클릭 합니다.

10. **추가할 값** \<필드에 HOST/sba fqdn\> 을 입력 합니다. 여기서 \<sba fqdn\> 은 Survivable Branch 기기의 fqdn (정규화 된 도메인 이름)입니다. 예를 들어 **HOST/BranchOffice1**를 입력 합니다.

11. **확인** 을 클릭 하 여 **servicePrincipalName** 특성 설정을 저장 한 다음 **확인** 을 클릭 하 여 컴퓨터 개체 속성을 저장 합니다.

12. **Active Directory 사용자 및 컴퓨터**에서 **사용자**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 클릭 한 다음 **사용자**를 클릭 합니다.

13. 마법사에 정보를 입력 하 여 Survivable Branch 기기 기술자에 대 한 도메인 사용자 계정을 만듭니다.

14. **Active Directory 사용자 및 컴퓨터**에서 **사용자**를 클릭 하 고 사용자 개체를 마우스 오른쪽 단추로 클릭 한 다음 **그룹에 추가**를 클릭 합니다.

15. **선택할 개체 이름을 입력**하 고 **RTCUniversalSBATechnicians**을 입력 한 다음 **확인**을 클릭 합니다.

16. 각 지사 사이트 기술자에 대해 12-15 단계를 반복 합니다.

**다음 단계**: [Lync Server 2013에서 토폴로지에 지점 사이트 추가](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

