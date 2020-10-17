---
title: 'Lync Server 2013: 스마트 카드 인증용으로 엔터프라이즈 CA 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abfbbb7a7f7787ab5490db1542c4435368a84ca0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532565"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Lync Server 2013에서 스마트 카드 인증용 엔터프라이즈 CA 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-03_

다음 섹션에서는 스마트 카드 인증을 지원 하도록 엔터프라이즈 루트 CA (인증 기관)를 구성 하는 방법을 설명 합니다. 엔터프라이즈 루트 CA를 설치 하는 방법에 대 한 자세한 내용은에서 엔터프라이즈 루트 인증 기관 설치를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) .

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>스마트 카드 인증을 지원 하도록 엔터프라이즈 루트 인증 기관 구성

다음 단계에서는 스마트 카드 인증을 지원 하도록 엔터프라이즈 루트 CA를 구성 하는 방법을 설명 합니다.

1.  도메인 관리자 계정을 사용 하 여 엔터프라이즈 CA 컴퓨터에 로그인 합니다.

2.  System Manager를 시작 하 고 인증 기관 웹 등록 역할이 설치 되어 있는지 확인 합니다.

3.  **관리 도구** 메뉴에서 **인증 기관** 관리 콘솔을 엽니다.

4.  탐색 창에서 **인증 기관을**확장 합니다.

5.  **인증서 템플릿을**마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 선택한 다음 **발급할 인증서 템플릿을**선택 합니다.

6.  **등록 에이전트**, **스마트 카드 사용자**및 **스마트 카드 로그온**을 선택 합니다.

7.  **확인**을 클릭합니다.

8.  **인증서 템플릿을**마우스 오른쪽 단추로 클릭 합니다.

9.  **관리**를 선택 합니다.

10. 스마트 카드 사용자 서식 파일의 속성을 엽니다.

11. **보안** 탭을 클릭 합니다.

12. 사용 권한을 다음과 같이 변경 합니다.
    
      - 읽기/등록 (허용) 권한을 사용 하 여 개별 사용자 AD 계정을 추가 하거나
    
      - 읽기/등록 (허용) 권한을 가진 스마트 카드 사용자를 포함 하는 보안 그룹을 추가 하거나
    
      - 읽기/등록 (허용) 권한을 사용 하 여 Domain Users 그룹 추가

</div>

</div>

<span> </span>

</div>

</div>

</div>

