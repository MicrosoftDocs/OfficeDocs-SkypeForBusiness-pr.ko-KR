---
title: 'Lync Server 2013: AD FS 2.0 (Active Directory Federation Services) 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c82c1ad2072f5f8611660efc44a502249f26d21b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Lync Server 2013에 대 한 AD FS 2.0 (Active Directory Federation Services) 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-03_

다음 섹션에서는 다단계 인증을 지원 하도록 AD FS 2.0 (Active Directory Federation Services)를 구성 하는 방법을 설명 합니다. AD FS 2.0을 설치 하는 방법에 대 한 자세한 내용은 AD FS 2.0 단계별 및 How To 가이드를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).

<div class="">


> [!NOTE]  
> AD FS 2.0을 설치할 때 Windows Server Manager를 사용 하 여 Active Directory Federation Services 역할을 추가 하지 마세요. 대신,에서 <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>Active Directory Federation Services 2.0 rtw 패키지를 다운로드 하 여 설치 합니다.



</div>

<div>


**2 단계 인증을 사용 하도록 AD FS를 구성 하려면**

1.  도메인 관리자 계정을 사용 하 여 AD FS 2.0 컴퓨터에 로그인 합니다.

2.  Windows PowerShell을 시작 합니다.

3.  Windows PowerShell 명령줄에서 다음 명령을 실행 합니다.
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  다음 명령을 실행 하 여 수동 인증을 사용 하도록 설정 되는 Lync Server 2013에 대 한 누적 업데이트를 포함 하는 각 Lync Server 2013:7 2013 월, Enterprise 풀 및 Standard Edition server에 대 한 파트너 관계를 설정 합니다. 배포와 관련 한 서버 이름:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  관리 도구 메뉴에서 AD FS 2.0 관리 콘솔을 실행 합니다.

6.  **트러스트 관계** \> **신뢰 당사자 트러스트**를 확장 합니다.

7.  Lync server 2013에 대 한 누적 업데이트, 2013 년 7 2013 월 엔터프라이즈 풀 또는 Standard Edition Server에 대 한 새 신뢰가 만들어졌는지 확인 합니다.

8.  다음 명령을 실행 하 여 Windows PowerShell을 사용 하 여 신뢰 당사자 트러스트에 대 한 발급 권한 부여 규칙을 만들고 할당 합니다.
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  다음 명령을 실행 하 여 Windows PowerShell을 사용 하 여 신뢰 당사자 트러스트에 대 한 발급 변환 규칙을 만들고 할당 합니다.
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. AD FS 2.0 관리 콘솔에서 신뢰 당사자 트러스트를 마우스 오른쪽 단추로 클릭 하 고 **클레임 규칙 편집**을 선택 합니다.

11. **발급 권한 부여 규칙** 탭을 선택 하 고 새 인증 규칙이 만들어졌는지 확인 합니다.

12. **발급 변환 규칙** 탭을 선택 하 고 새 변환 규칙이 만들어졌는지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

