---
title: 관리자를 위한 비즈니스용 Skype Online 로그인 오류 문제 해결
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '비즈니스용 Skype Online 로그인 오류의 일반적인 원인을 알아보고 이들을 해결하는 방법에 대해 알아보세요. '
ms.openlocfilehash: c8cef553946dbe19a4a986e3ccaf714ad0a689de
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580012"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>관리자를 위한 비즈니스용 Skype Online 로그인 오류 문제 해결

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

비즈니스용 Skype Online 로그인 오류 문제를 해결하기 위해서는 로그인 문제의 가장 일반적인 원인을 제거하면서 시작합니다. 이후 필요에 따라 오류의 유형에 따라 특정 해결 단계를 따라 수행할 수 있습니다. 사용자가 여전히 로그인할 수 없는 경우 추가 정보를 수집한 다음 추가 도움말을 검색합니다.

## <a name="what-do-you-want-to-do"></a>무슨 작업을 수행하시겠습니까?
<a name="top"> </a>

> [비즈니스용 Skype Online 로그인 오류의 일반적인 원인을 확인](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
> 
> [특정 오류에 대한 해결 단계를 수행 (엔터프라이즈의 경우만 해당)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
> 
> [사용자의 프록시 서버에 msoidsvc.exe에 대 한 방화벽 항목을 추가](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
> 
> [DNS 설정 업데이트](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
> 
> [ADFS 서버에 타사의 SSL 인증서를 설치](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
> 
> [보안 자격 증명 업데이트](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
> 
> [TrustModelData 레지스트리 키 수정](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
> 
> [Active Directory에서 사용자 설정 업데이트](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
> 
> [Microsoft 지원 문제 해결 가이드 사용](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
> 
> [추가 정보를 수집 및 추가 도움말 검색](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>비즈니스용 Skype Online 로그인 오류의 일반적인 원인을 확인
<a name="toc323194094"> </a>

대부분의 로그인 문제는 소수의 원인으로 추적할 수 있으며,이 중 상당수는 손쉽게 해결할 수 있습니다. 아래의 표에는 로그인 오류의 일반적인 원인들과 사용자가 문제를 해결하기 위해 수행할 수 있는 몇 가지 단계가 나와 있습니다.


| **가능한 원인**                                                                                                                                                    | **해결 방법**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 로그인하는 동안 다음의 문구가 포함된 대화 상자가 표시됩니다: **사용자의 로그인 주소에 대해 이 서버가 신뢰할 수 있는 서버인지 확인할 수 없습니다. 그래도 연결하시겠습니까?** <br/> | 대화 상자의 도메인 이름이 **domainName.contoso.com** 과 같이 조직에서 신뢰할 수 있는 서버인지 확인합니다. 사용자에게 **해당 서버를 항상 신뢰** 확인란을 선택하도록 요청하고 **연결** 을 클릭합니다. <br/> 기업 고객은 각 사용자의 컴퓨터에서 Windows 레지스트리를 수정하여 사용자가 처음 로그인할 때 이 메시지가 나타나지 않도록 방지할 수 있습니다. 자세한 내용은 [TrustModelData 레지스트리 키 수정](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)을 참조하세요.<br/> |
| 로그인 주소, 사용자 이름 또는 비밀번호를 잘못 입력했습니다.  <br/>                                                                                                               | 사용자의 로그인 이름 및 비밀번호가 올바른지 확인합니다. <br/>  사용자의 로그인 이름 형식이 다음과 같은지 확인합니다: <strong>bobk@contoso.com</strong>. 이는 조직의 네트워크에 로그인하는 데 사용되는 형식과 다를 수 있습니다.  <br/>  사용자에게 다시 로그인하도록 요청합니다. <br/>                                                                                                                                                                                                                             |
| 비밀번호를 잊어버렸습니다.  <br/>                                                                                                                                             | 사용자의 비밀번호를 다시 설정하고 새 임시 비밀번호를 알려줍니다.  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| 비즈니스용 Skype Online 사용 권한이 부여되지 않음  <br/>                                                                                                                  | 사용자가 비즈니스용 Skype Online 사용자로 등록 되어있는지 확인합니다. 등록되어 있지 않은 경우 사용자를 등록한 후 사용자에게 다시 로그인하도록 요청합니다.  <br/>                                                                                                                                                                                                                                                                                                                                                                                           |
| 설치된 비즈니스용 Skype Online이 잘못된 버전입니다.  <br/>                                                                                                           | 이 문제는 주로 **인증 서비스가 이 프로그램 버전과 호환되지 않을 수 있습니다** 라는 내용의 오류 메시지와 관련이 있습니다.  <br/> 사용자에게 Microsoft 365 관리 센터에서 비즈니스용 Skype Online을 제거했다가 다시 설치하도록 요청합니다.  <br/>                                                                                                                                                                                                                                                    |
| 로그인하는 데 필요한 개인 인증서를 가져오는 동안 문제가 발생했습니다.  <br/>                                                                                           | 사용자의 로그인 주소가 최근에 변경되었으면 캐시된 로그인 데이터를 삭제해야 할 수 있습니다. 사용자에게 로그아웃을 요청하고 로그인 화면에서 내 로그인 정보 삭제 링크를 클릭한 후, 다시 시도하세요.  <br/>                                                                                                                                                                                                                                                                                                                                |
| 사용자 지정 도메인 이름을 설정했지만 변경 내용이 시스템 전체로 아직 모두 전파되지 않았을 수 있습니다.  <br/>                                                         | 먼저 변경 내용을 반영하도록 DNS(도메인 이름 서비스) 레코드를 수정했는지 확인합니다.  <br/> 필수 DNS 변경 내용을 이미 작성한 경우에는 사용자에게 나중에 로그인을 시도하도록 요청합니다. DNS 변경 내용이 시스템 전체에 적용되는 데 최대 72시간이 걸릴 수 있습니다.  <br/>                                                                                                                                                                                                                                                        |
| 시스템 시계가 서버 시계와 동기화되지 않았습니다.  <br/>                                                                                                                     | 네트워크 도메인 컨트롤러가 신뢰할 만한 외부 시간 소스와 동기화되어 있는지 확인합니다. 자세한 내용은 Microsoft Knowledge Base 문서 816042, [Windows Server에서 권한이 있는 시간 서버 구성 방법](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)을 참조하세요.<br/>                                                                                                                                                                                                                                          |

비즈니스용 Skype Online 로그인 오류 문제를 해결하기 위해서는 로그인 문제의 가장 일반적인 원인을 제거하면서 시작합니다. 이후 필요에 따라 오류의 유형에 따라 특정 해결 단계를 따라 수행할 수 있습니다. 사용자가 여전히 로그인할 수 없는 경우 추가 정보를 수집한 다음 추가 도움말을 검색합니다.

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>특정 오류에 대한 해결 단계를 따라 수행 (엔터프라이즈의 경우만 해당)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  이 지침은 우선적으로 Microsoft Office 365 플랜 E의 고객을 대상으로 작성되었습니다. Office 365 플랜 P 고객의 경우 다음 섹션으로 이동하여 [자세한 정보를 수집하고 추가 도움말을 검색합니다](troubleshooting-sign-in-errors-for-admins.md#collect-more-information).

이전 섹션에서의 제안을 시도한 후에도 사용자가 로그인할 수 없는 경우 오류 유형에 따라 추가 문제 해결 방법을 따라 수행할 수 있습니다. 아래의 표에는 가장 일반적인 오류 메시지와 잠정 원인들이 열거되어 있습니다. 다음의 표는 각 문제를 해결하기 위한 세부 절차입니다.

|**오류 메시지**|**잠정 원인**|**해결 방법**|
|:-----|:-----|:-----|
|로그인 주소를 찾을 수 없습니다:  <br/> |Microsoft Online Services Sign-On Assistant (msoidsvc.exe)를 통한 로그인 요청이 외부 방화벽이나 프록시 서버로 전달되지 않습니다.  <br/> |[사용자의 프록시 서버에 msoidsvc.exe에 대 한 방화벽 항목을 추가](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|일시적으로 서버를 사용할 수 없습니다  <br/> |조직에 사용자 지정 도메인이 있는 경우 필수 DNS (도메인 이름 시스템)의 설정이 누락되거나 잘못되었을 수 있습니다.  <br/> |[DNS 설정 업데이트](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|일시적으로 서버를 사용할 수 없습니다  <br/> |조직에서 ADFS (Active Directory Federation Services)에 통합 인증을 사용하는 경우 타사 인증 기관에서 보낸 것이 아닌 자체적으로 서명된 SSL (보안 소켓 계층) 인증서를 사용했을 수 있습니다.  <br/> |[ADFS 서버에 타사의 SSL 인증서를 설치](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|로그인하는 데 필요한 개인 인증서를 가져오는 동안 문제가 발생했습니다.  <br/> |로그인 하는 데 사용되는 캐시된 서버 데이터를 이미 제거하였고 오류가 계속 표시되는 경우 사용자의 보안 자격 증명이 손상되었거나 사용자 컴퓨터의 RSA 폴더가 인증을 차단하고 있을 수 있습니다.  <br/> |[보안 자격 증명 업데이트](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|사용자가 처음 로그인할 때 인증서 신뢰 대화 상자가 나타납니다.  <br/> |이 대화 상자는 사용자의 비즈니스용 Skype 서버가 아직 **TrustModelData** 레지스트리 키에 열거되지 않은 경우에 나타납니다. <br/> |[TrustModelData 레지스트리 키 수정](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|사용자가 SIP를 사용하도록 설정되어 있지 않습니다  <br/> |조직에서 Microsoft Office Communications Server 또는 Microsoft Lync Server 2010를 이전에 설치한 경우 서버를 제거하기 전에 사용자를 서버에서 삭제하지 않았을 수 있습니다. 따라서 **msRTCSIP-UserEnabled** 속성이 Active Directory Domain Services에서 아직 **FALSE** 로 설정되어 있습니다. <br/> |[Active Directory에서 사용자 설정 업데이트](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>사용자의 프록시 서버의 msoidsvc.exe에 방화벽 항목을 추가
<a name="add-a-firewall"> </a>

이 절차는 다음의 오류 메시지에 대한 문제를 해결할 수 있습니: **로그인 주소를 찾을 수 없습니다**.

> [!NOTE]
> 다음 단계에서는 사용자가 Microsoft Forefront Threat Management Gateway (TMG) 2010을 사용 하고 있다고 가정합니다. 다른 웹 게이트웨이 솔루션을 사용하는 경우 아래 4단계에서 설명하는 설정을 사용합니다.


Forefront TMG 2010에서 Msoidsvc.exe의 프로그램 항목을 만들려면 다음의 단계를 따릅니다:

1. Forefront의 왼쪽 창에서 **네트워킹** 을 클릭 합니다.

2. **네트워크** 탭을 클릭합니다. 오른쪽 창의 **작업** 탭에서 **Forefront TMG 클라이언트 설정 구성** 을 클릭합니다.

3. **Forefront TMG 클라이언트 설정** 대화 상자에서 **새로 설정** 을 클릭합니다.

4. **응용 프로그램 항목 설정** 대화 상자에서 다음의 규칙을 구성합니다:

|**응용 프로그램**|**키**|**값**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |비활성화  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

자세한 내용은 Microsoft Knowledge Base 문서 2409256, [온-프레미스 방화벽이 연결을 차단하기 때문에 비즈니스용 Skype Online에 연결할 수 없습니다](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)를 참조하세요.

### <a name="update-dns-settings"></a>DNS 설정 업데이트
<a name="update-dns-service"> </a>

조직에 사용자 지정 도메인이 있는 경우 이 절차는 다음과 같은 오류 메시지를 수정하는 데 사용할 수 있습니다: **서버를 일시적으로 사용할 수 없습니다**.

- 도메인에 다음의 CNAME 레코드를 추가하는 방법에 대해서 도메인 이름 등록 부서에 문의합니다.

  - **DNS 레코드 형식**: CNAME

  - **이름**: sip

  - **값/대상**: sipdir.online.lync.com

자세한 내용은 Microsoft Knowledge Base 문서 2566790, [Microsoft 365 또는 Office 365에서 비즈니스용 Skype Online DNS 구성 문제 해결](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)을 참조하세요.

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>ADFS 서버에 타사의 SSL 인증서 설치
<a name="verify-upn-and"> </a>

ADFS (Active Directory Federation Services) 서버에 타사의 SSL 인증서를 설치하려면 다음의 단계를 따릅니다:

1. VeriSign이나 Thawte와 같은 타사의 인증 기관에서 SSL 인증서를 받습니다.

2. ADFS 관리 콘솔을 사용하여 ADFS 서버에 인증서를 설치합니다.

### <a name="update-security-credentials"></a>보안 자격 증명 업데이트
<a name="update-security-credentials"> </a>

이 절차는 오류 메시지 **로그인하는데 필요한 개인 인증서를 가져오는데 문제가 있습니다** 에 대한 잠정 해결 방법입니다.

잠정 인증서 또는 자격 증명 문제를 없애려면 먼저 Windows Certificate Manager에서 사용자의 인증서를 갱신합니다. 이 작업을 수행하려면 다음 단계를 따르세요.

1. Windows Certificate Manager를 엽니다. **시작**, **실행** 을 차례로 클릭하고 **certmgr.msc** 을 입력한 다음 **확인** 을 클릭합니다.

2. **개인** 을 두 번 클릭하고 **인증서** 를 두 번 클릭합니다.

3. **발행 주체** 열로 정렬한 다음 Communications Server에서 발행한 인증서를 찾습니다.

4. 인증서를 마우스 오른쪽 버튼으로 클릭하고 **삭제** 를 클릭합니다.

다음으로, Windows 7을 실행 중인 경우 Windows Credential Manager에서 저장된 자격 증명을 제거합니다. 이 작업을 수행하려면 다음 단계를 따르세요.

1. **시작**, **제어판** 을 차례로 클릭하고 **자격 증명 관리자** 를 클릭합니다.

2. 비즈니스용 Skype Online에 연결하는 데 사용되는 자격 증명 집합을 찾습니다.

3. 자격 증명 집합을 확장한 다음 **저장실에서 제거** 를 클릭합니다.

4. 다시 로그인하고 사용자의 자격 증명을 다시 입력합니다.

마지막으로 자격 증명을 업데이트한 후에도 사용자가 계속해서 로그인할 수 없으면 사용자 인증 프로세스의 완료를 RSA 폴더가 차단하고 있을 스 있기에 사용자 컴퓨터에서 RSA 폴더를 삭제 합니다:

1. 관리자 계정을 사용하여 사용자의 컴퓨터에 로그인 합니다.

2. 필요한 경우 폴더 보기 옵션 **숨긴 파일 보기** 를 활성화합니다.

3. 파일 탐색기의 주소 표시줄에 다음을 입력합니다. **C: \\Documents and Settings\\UserName\\Application Data\\Microsoft\\Crypto\\RSA**. 여기에서 **_UserName_** 은 Windows 로그인 이름입니다.

4. **S-1-5-21-** 로 시작하여 다음에 숫자 문자열이 붙는 이름을 가진 모든 폴더를 삭제합니다.

### <a name="modify-trustmodeldata-registry-keys"></a>TrustModelData 레지스트리 키 수정
<a name="modify-trustmodeldata-registry"> </a>

용자가 처음 로그인하는 경우에는 다음과 같은 메시지가 포함된 대화 상자가 표시될 수 있습니다: **사용자의 로그인 주소에 대해 이 서버가 신뢰할 수 있는 서버인지 확인할 수 없습니다. 그래도 연결하시겠습니까?** 이 대화 상자는 Outlook의 보안 기능으로서 오류가 아닙니다. 그러나 GPO (그룹 정책 개체)를 사용하여 사용자가 최초로 로그인하기 전에 사용자의 컴퓨터 도메인 이름을 업데이트하여 대화 상자가 나타나지 않도록 할 수 있습니다. 그 절차는 다음과 같습니다:

- 비즈니스용 Skype 도메인 이름 (예: domainName.contoso.com)을 덧붙이는 GPO를 만들고 HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData의 현재 값에 배포합니다.

> [!IMPORTANT]
>  도메인 이름으로 기존 값을 대체하는 것이 아니라 기존 값에 *덧붙여야* 합니다.

자세한 내용은 Microsoft Knowledge Base 문서 2531068, [비즈니스용 Skype (Lync)에서 서버가 로그인 주소에 대해 신뢰할 수 있는지 확인할 수 없습니다](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)를 참조하세요.

### <a name="update-user-settings-in-active-directory"></a>Active Directory에서 사용자 설정 업데이트
<a name="update-user-settings"> </a>

조직에서 Microsoft Office Communications Server 또는 Microsoft Lync Server 2010를 이전에 설치한 경우 서버를 제거하기 전에 사용자를 서버에서 삭제하지 않았을 수 있습니다. 따라서 **msRTCSIP-UserEnabled** 속성이 Active Directory Domain Services에서 아직 **FALSE** 로 설정되어 있습니다.

이 문제를 해결하려면 다음의 단계를 수행합니다:

1. 영향을 받는 모든 사용자의 **msRTCSIP- UserEnabled** 속성을 **TRUE** 로 업데이트합니다.

2. Microsoft Online Services DirSync(디렉터리 동기화)도구를 반환합니다. 자세한 내용은 [Azure Active Directory와 온-프레미스 디렉터리 통합](/azure/active-directory/hybrid/whatis-hybrid-identity)을 참조하세요.

비즈니스용 Skype Online 로그인 오류 문제를 해결하기 위해서는 로그인 문제의 가장 일반적인 원인을 제거하면서 시작합니다. 이후 필요에 따라 오류의 유형에 따라 특정 해결 단계를 따라 수행할 수 있습니다. 사용자가 여전히 로그인할 수 없는 경우 추가 정보를 수집한 다음 추가 도움말을 검색합니다.
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Microsoft 지원 문제 해결 가이드 사용
<a name="toc325626447"> </a>

계속해서 사용자의 로그인 문제를 해결할 수 없는 경우 Microsoft Knowledge Base 문서 2541980, [비즈니스용 Skype Online의 로그인 문제를 해결하는 방법](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)을 참조하세요.

## <a name="collect-more-information-and-seek-additional-help"></a>추가 정보를 수집 및 추가 도움말 검색
<a name="collect-more-information"> </a>

위의 지침을 따른 후에도 여전히 로그인 문제를 해결할 수 없는 경우 추가 정보를 수집하고 기술지원센터에 문의해야 합니다. 이 작업을 수행하려면 다음 단계를 따르세요.

1. 사용자의 기기에서 로그 파일 및 Windows 이벤트 로그의 세부 정보를 가져옵니다. 단계별 지침은 최종사용자 도움말 주제 [Lync에서 오류 로그를 활성화](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)를 참조하세요.

2. 로그 파일 및 오류에 대한 자세한 정보를 Microsoft 기술지원센터에 보냅니다.

영향을 받는 사용자의 기기에 Microsoft Online Services 진단 및 로깅 (MOSDAL) 지원 도구 키트를 설치하여 추가 진단 정보를 제공하라는 요청 메시지가 표시될 수도 있습니다. 자세한 내용은 [MOSDAL 지원 툴킷 활용](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)을 참조하세요.

비즈니스용 Skype Online 로그인 오류 문제를 해결하기 위해서는 로그인 문제의 가장 일반적인 원인을 제거하면서 시작합니다. 이후 필요에 따라 오류의 유형에 따라 특정 해결 단계를 따라 수행할 수 있습니다. 사용자가 여전히 로그인할 수 없는 경우 추가 정보를 수집한 다음 추가 도움말을 검색합니다.

## <a name="related-topics"></a>관련 주제
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)
