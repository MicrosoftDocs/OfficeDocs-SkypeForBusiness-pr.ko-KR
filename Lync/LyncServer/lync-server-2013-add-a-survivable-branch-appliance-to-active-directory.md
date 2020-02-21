---
title: 'Lync Server 2013: Active Directory에 Sba (survivable 분기 기기 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25d8efb03b4d67b6409f93b6a99d2314cb703952
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Lync Server 2013에서 Active Directory에 Sba (survivable Branch 기기 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-23_

Sba (survivable 분기 기기를 배포 하려는 경우 Active Directory 도메인 서비스에 Sba (survivable 분기 어플라이언스를 추가 해야 합니다. 이 절차는 중앙 사이트에서 수행합니다.

<div>


> [!IMPORTANT]  
> Sba (survivable 분기 기기를 배포 하는 경우에만이 절차를 수행 합니다. Sba (survivable 분기 서버를 배포 하는 경우에는이 작업을 수행 하지 마십시오.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>Survivable Branch Appliance를 Active Directory 도메인 서비스에 추가하려면

1.  Enterprise Admins 그룹의 구성원으로 구성원 서버에 로그온합니다.

2.  **시작**, **관리 도구**, **Active Directory 사용자 및 컴퓨터**를 차례로 클릭합니다.

3.  **동작** 메뉴에서 **새로 만들기**를 클릭한 다음 **컴퓨터**를 클릭합니다.

4.  **새 개체-컴퓨터** 대화 상자에서 Sba (survivable Branch 기기 컴퓨터 개체의 이름 (예:: branchoffice1)을 입력 하 고 **변경을**클릭 합니다.

5.  **사용자 또는 그룹 선택** 대화 상자에서 RTCUniversalSBATechnicians 그룹을 추가하고 **확인**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 분기 사이트의 RTCUniversalSBATechnicians 그룹 구성원이 나중에 이 장치를 도메인에 추가합니다.

    
    </div>

6.  **확인** 을 클릭 하 여 Sba (survivable Branch 기기 computer 개체를 저장 합니다.

7.  **시작**, **관리 도구**를 차례로 클릭한 다음 **ADSI 편집**을 클릭합니다.

8.  **ADSI 편집**에서, 이전 단계에서 만든 컴퓨터 개체를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.

9.  특성 목록에서 **servicePrincipalName**을 클릭하고 **편집**을 클릭합니다.

10. **추가할 값** \<필드에 호스트/sba fqdn\> , 여기서 \<sba fqdn\> 은 sba (survivable Branch 기기의 fqdn (정규화 된 도메인 이름)을 입력 합니다. 예를 들어 **HOST/: branchoffice1**를 입력 합니다.

11. **확인**을 클릭하여 **servicePrincipalName** 특성 설정을 저장하고 **확인**을 클릭하여 컴퓨터 개체 속성을 저장합니다.

12. **Active Directory 사용자 및 컴퓨터**에서 **사용자**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 클릭한 후에 **사용자**를 클릭합니다.

13. 마법사에 정보를 입력 하 여 Sba (survivable Branch 어플라이언스 기술자에 대 한 도메인 사용자 계정을 만듭니다.

14. **Active Directory 사용자 및 컴퓨터**에서 **사용자**를 클릭하고 사용자 개체를 마우스 오른쪽 단추로 클릭한 후에 **그룹에 추가**를 클릭합니다.

15. **선택할 개체 이름을 입력하십시오**에 **RTCUniversalSBATechnicians**를 입력하고 **확인**을 클릭합니다.

16. 각 분기 사이트 기술자에 대해 12-15단계를 반복합니다.

**다음 단계**: [Lync Server 2013에서 분기 사이트를 토폴로지에 추가](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

