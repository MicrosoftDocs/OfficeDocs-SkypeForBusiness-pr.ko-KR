---
title: Lync Server 2013:2 단계 인증 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba76bbc896c1da2929a584611af0607a51d5afcc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Lync Server 2013의 2 단계 인증 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-04-06_

다음은 2 단계 인증을 지원 하기 위해 Microsoft Lync Server 2013 환경을 구성할 때의 배포 고려 사항 목록입니다.

<div>

## <a name="client-support"></a>클라이언트 지원

Lync Server 2013에 대 한 Lync 2013 누적 업데이트: 7 월 2013 데스크톱 클라이언트 및 모든 모바일 클라이언트는 현재 2 단계 인증을 지원 합니다.

</div>

<div>

## <a name="topology-requirements"></a>토폴로지 요구 사항

고객은 Lync Server 2013에 대 한 누적 업데이트와 함께 전용 Lync Server 2013을 사용 하 여 2 단계 인증을 배포 하는 것이 좋습니다 (2013 년 7 월, 디렉터 및 사용자 풀). Lync 사용자에 대해 수동 인증을 사용 하도록 설정 하려면 다음을 비롯 한 다른 역할 및 서비스에 대해 다른 인증 방법을 사용 하지 않도록 설정 해야 합니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>구성 유형</th>
<th>서비스 종류</th>
<th>서버 역할</th>
<th>사용 하지 않도록 설정할 인증 유형</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>웹 서비스</p></td>
<td><p>System.webserver</p></td>
<td><p>영화</p></td>
<td><p>Kerberos, NTLM 및 인증서</p></td>
</tr>
<tr class="even">
<td><p>웹 서비스</p></td>
<td><p>System.webserver</p></td>
<td><p>프런트 엔드</p></td>
<td><p>Kerberos, NTLM 및 인증서</p></td>
</tr>
<tr class="odd">
<td><p>프록시와</p></td>
<td><p>EdgeServer</p></td>
<td><p>면</p></td>
<td><p>Kerberos 및 NTLM</p></td>
</tr>
<tr class="even">
<td><p>프록시와</p></td>
<td><p>등록자</p></td>
<td><p>프런트 엔드</p></td>
<td><p>Kerberos 및 NTLM</p></td>
</tr>
</tbody>
</table>


서비스 수준에서 이러한 인증 유형을 사용 하지 않도록 설정 하지 않으면 배포 내에서 2 단계 인증을 사용 하는 경우 다른 모든 버전의 Lync 클라이언트에서 성공적으로 로그인 할 수 없습니다.

</div>

<div>

## <a name="lync-service-discovery"></a>Lync 서비스 검색

내부 및/또는 외부 클라이언트가 Lync services를 검색 하는 데 사용 하는 DNS 레코드는 2 단계 인증을 사용 하도록 설정 되지 않은 Lync 서버로 확인 되도록 구성 해야 합니다. 이 구성을 사용 하는 경우 2 단계 인증을 사용 하도록 설정 되지 않은 Lync 풀의 사용자는 인증에 PIN을 입력 하지 않아도 되 고, 2 단계 인증을 사용 하는 Lync 풀의 사용자는 PIN을 입력 해야 합니다. 받고.

</div>

<div>

## <a name="exchange-authentication"></a>Exchange 인증

Microsoft Exchange에 대해 2 단계 인증을 배포한 고객은 Lync 클라이언트의 특정 기능을 사용할 수 없습니다. 이는 Lync 클라이언트가 Exchange 통합에 의존 하는 기능에 대해 2 단계 인증을 지원 하지 않으므로 현재 의도적으로 설계 된 것입니다.

</div>

<div>

## <a name="lync-contacts"></a>Lync 대화 상대

통합 연락처 저장소 기능을 활용 하도록 구성 된 Lync 사용자는 2 단계 인증을 사용 하 여 로그인 한 후 해당 연락처를 더 이상 사용할 수 없습니다.

2 단계 인증을 사용 하도록 설정 하기 전에 **invoke-csucsrollback** cmdlet을 사용 하 여 통합 연락처 저장소에서 기존 사용자 연락처를 제거한 후 Lync Server 2013에 저장 해야 합니다.

</div>

<div>

## <a name="skill-search"></a>기술 검색

Lync 환경에서 기술 검색 기능을 구성한 고객은 Lync가 2 단계 인증을 사용 하도록 설정 된 경우이 기능이 작동 하지 않는 것을 확인할 수 있습니다. 이는 Microsoft SharePoint에서 현재 2 단계 인증을 지원 하지 않으므로 의도적으로 설계 된 것입니다.

</div>

<div>

## <a name="lync-credentials"></a>Lync 자격 증명

2 단계 인증을 사용 하도록 구성 된 사용자에 게 영향을 줄 수 있는 저장 된 Lync 자격 증명과 관련 한 몇 가지 배포 고려 사항이 있습니다.

<div>

## <a name="deleting-saved-credentials"></a>저장 된 자격 증명 삭제

데스크톱 클라이언트 사용자는 2 단계 인증을 사용 하 여 처음으로 서명을 시도 하기 전에 Lync 클라이언트에서 **내 로그인 정보 삭제** 옵션을 사용\\하\\고\\%\\localappdata% Microsoft Office 15.0 Lync에서 SIP 프로필 폴더를 삭제 해야 합니다.

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Kerberos 또는 NTLM 인증 방법을 사용 하는 경우 인증을 위해 사용자의 Windows 자격 증명이 자동으로 사용 됩니다. Kerberos 및/또는 NTLM이 인증을 사용 하도록 설정 된 일반적인 Lync Server 2013 배포에서는 사용자가 로그인 할 때마다 자격 증명을 입력 하지 않아도 됩니다.

사용자에 게 PIN을 입력 하 라는 메시지가 표시 되기 전에 실수로 자격 증명을 묻는 메시지가 표시 되는 경우에는 그룹 정책을 통해 클라이언트 컴퓨터에서 **DisableNTCredentials** 레지스트리 키가 실수로 구성 될 수 있습니다.

자격 증명에 대 한 추가 확인을 방지 하려면 로컬 워크스테이션에 다음 레지스트리 항목을 만들거나, 그룹 정책을 사용 하 여 지정 된 풀에 대 한 모든 사용자에 게 Lync 관리 템플릿을 사용 하 여 적용 합니다.

HKEY\_로컬\_컴퓨터\\소프트웨어\\정책\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD: DisableNTCredentials

값: 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

사용자가 처음 Lync에 로그인 할 때 사용자에 게 암호를 저장 하 라는 메시지가 표시 됩니다. 이 옵션을 선택 하면 사용자의 클라이언트 인증서를 개인 인증서 저장소에 저장 하 고 사용자의 Windows 자격 증명을 로컬 컴퓨터의 자격 증명 관리자에 저장할 수 있습니다.

Lync가 2 단계 인증을 지원 하도록 구성 된 경우에는 **Savepassword** 레지스트리 설정을 사용 하지 않도록 설정 해야 합니다. 사용자가 암호를 저장 하지 못하도록 하려면 로컬 워크스테이션에서 다음 레지스트리 항목을 변경 하거나, 그룹 정책을 사용 하 여 지정 된 풀에 대 한 모든 사용자에 게 Lync 관리 템플릿을 사용 하 여 적용 합니다.

HKEY\_현재\_사용자\\소프트웨어\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD: SavePassword

값: 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 토큰 재생

AD FS 2.0는 동일한 토큰을 사용 하는 여러 토큰 요청을 검색 한 다음 삭제할 수 있는 토큰 재생 검색 이라는 기능을 제공 합니다. 이 기능을 사용 하도록 설정 하면 토큰 재생 검색 기능이 WS-FEDERATION 수동 프로필과 SAML Websso) 프로필 둘 다에서 인증 요청의 무결성을 보호 하 여 동일한 토큰을 두 번 이상 사용 하지 않도록 합니다.

이 기능은 보안을 사용 하는 경우 키오스크를 사용할 때와 같이 보안이 매우 중요 한 상황에서 사용 하도록 설정 해야 합니다. 토큰 재생 검색에 대 한 자세한 내용은 Secure FS 2.0의 보안 계획 및 배포 모범 사례를 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).

</div>

<div>

## <a name="external-user-access"></a>외부 사용자 액세스

외부 네트워크에서 Lync 2 단계 인증을 지원 하도록 AD FS 프록시 또는 역방향 프록시를 구성 하는 것은 이러한 항목에서 다루지 않습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

