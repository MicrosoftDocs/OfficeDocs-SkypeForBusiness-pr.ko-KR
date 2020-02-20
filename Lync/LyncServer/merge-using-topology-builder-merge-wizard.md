---
title: 토폴로지 작성기 병합 마법사를 사용 하 여 병합
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8578217d5e3b35351937dbf2838e2994e74fb32e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>토폴로지 작성기 병합 마법사를 사용 하 여 병합

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

1.  토폴로지 작성기를 사용하여 기존 배포를 다운로드합니다.

2.  **동작** 메뉴에서 **Office Communications Server 2007 R2 병합**을 선택합니다.

3.  **다음**을 클릭합니다.

4.  **에지 설정 지정**에서 **추가**를 클릭합니다.
    
    ![토폴로지 병합 마법사,에 지 설정 지정 페이지](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "토폴로지 병합 마법사,에 지 설정 지정 페이지")  

5.  **에지 유형 지정**에서 에지 서버 구성 유형을 입력하고 **다음**을 클릭합니다. 이 예에서는 **단일 에지 서버** 옵션이 사용됩니다.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>확장된 에지 배포</STRONG>는 지원되는 구성이 아닙니다. <STRONG>확장된 에지 서버</STRONG>가 먼저 <STRONG>단일 에지 서버</STRONG> 또는 <STRONG>부하 분산 통합 에지</STRONG> 서버로 변환되어야 합니다.

    
    </div>

6.  **내부에 지 설정 지정** 에서 필요에 따라에 지 풀의 내부 FQDN 및 포트에 대 한 관련 정보를 입력 한 후 **다음**을 클릭 합니다.
    
    ![내부에 지 설정 지정 대화 상자](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "내부에 지 설정 지정 대화 상자")  

7.  **외부 에지 지정**에서 에지 서버에 대한 웹 회의 FQDN 정보를 입력합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>다음</STRONG>을 클릭하기 전에 이 절차의 다음 단계를 수행합니다. 이 단계를 결코 건너뛰어서는 안 됩니다.

    
    </div>

8.  페더레이션을 위해 레거시 Office Communications Server 2007 R2에 지 서버를 사용 하려는 경우 **이에 지 풀은 페더레이션 및 공용 IM 연결에 사용 됩니다** 확인란을 선택 합니다. 여러 에지 서버를 배포한 경우 그중 한 에지 서버만 페더레이션에 사용하도록 설정됩니다. 이 확인란을 선택하지 않았는데 나중에 페더레이션을 사용할 것을 결정하는 경우 토폴로지 작성기 병합 마법사를 실행하여 토폴로지를 다시 게시해야 합니다.
    
    ![에 지 서버 대화 상자, 외부에 지 지정 페이지](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "에 지 서버 대화 상자, 외부에 지 지정 페이지")  

9.  **다음 홉 지정**에서 환경의 다음 홉 위치에 대한 FQDN(정규화된 도메인 이름)을 입력합니다. **마침**을 클릭합니다.
    
    ![에 지 서버 대화 상자, 다음 홉 지정 페이지](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "에 지 서버 대화 상자, 다음 홉 지정 페이지")  

10. 에 **지 설정 지정**에서 모든 Office Communications Server 2007 R2에 지 서버를 추가한 경우 **다음**을 클릭 합니다. 추가할 Office Communications Server 2007 R2에 지 서버가 더 있는 경우 4 단계부터이 절차를 반복 합니다.

11. **내부 sip 포트 지정** 에서 기본 설정 (기본 sip 포트를 수정 하지 않은 경우)을 선택 합니다. 기본 포트 5061을 사용하지 않는 경우 포트를 적절히 변경하고 **다음**을 클릭합니다.

12. **요약**에서 **다음**을 클릭하여 토폴로지 병합을 시작합니다.

13. 마법사 페이지에서 토폴로지가 성공적으로 병합되었는지 확인됩니다.

14. **상태** 열에서 값이 **성공**인지 확인한 후 **마침**을 클릭합니다.

15. 토폴로지 작성기의 왼쪽 창에 Office Communications Server 2007 R2 환경이 Lync Server 2013과 병합 되었음을 나타내는 **BackCompatSite**가 표시 됩니다.
    
    ![병합 된 토폴로지를 보여 주는 토폴로지 작성기](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "병합 된 토폴로지를 보여 주는 토폴로지 작성기")  

16. **동작** 메뉴에서 **토폴로지 게시**를 클릭하고 **다음**을 클릭합니다.

17. **게시 마법사**가 완료되면 **마침**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 기존 정책 설정을 Lync Server 2013로 가져오려면 다음 항목인 <A href="import-policies-and-settings.md">정책 및 설정 가져오기</A>를 완료 하는 것이 중요 합니다.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

