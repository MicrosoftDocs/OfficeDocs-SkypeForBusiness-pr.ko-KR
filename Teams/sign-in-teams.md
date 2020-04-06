---
title: 최신 인증을 사용하여 Teams에 로그인
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 최신 인증을 사용하여 Microsoft Teams에 로그인하는 방법 사용자가 Windows에 UPN을 무시하도록 지시하는 설정을 사용하여 로그인할 때 UPN 사용자 이름 추가를 자동으로 건너뛰는 방법이 포함되어 있습니다.
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5e61b1cb79b7c4e2989d823af2c6617337291cf6
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43138897"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>최신 인증을 사용하여 Microsoft Teams에 로그인
==========================

Microsoft Teams는 최신 인증을 사용하여 로그인 환경을 간편하고 안전하게 유지합니다. 사용자가 Teams에 로그인하는 방법을 보려면 [Teams 로그인](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)을 참조하세요.

## <a name="how-modern-authentication-works"></a>최신 인증이 작동하는 방식

최신 인증은 Teams에 사용자가 이미 사용자의 자격 증명(예: 직장 전자 메일 및 암호)을 다른 곳에 이미 입력했음을 알리고 앱을 시작하기 위해 다시 입력하지 않아도 되는 프로세스입니다. 사용자가 Windows 또는 Mac에서 작업하는 경우와 같이 몇 가지 요인에 따라 환경이 다를 수 있습니다. 또한 조직이 한 단계 인증 또는 다단계 인증을 사용하도록 설정했는지에 따라 다를 수 있습니다(다단계 인증에는 일반적으로 전화를 통한 자격 증명 확인, 고유 코드 제공, PIN 입력 또는 지문 제시가 포함됨). 다음은 최신 인증 시나리오에 대한 개요입니다.

### <a name="windows-users"></a>Windows 사용자 

- 사용자가 Office 365 Enterprise 계정을 통해 다른 Office 앱에 이미 로그인한 경우 Teams를 시작할 때 앱으로 바로 이동하게 됩니다. 사용자가 자격 증명을 입력할 필요가 없습니다.

- 사용자가 다른 곳에서 자신의 Office 365 Enterprise 계정에 로그인되어 있지 않은 경우 Teams를 시작할 때 조직에서 프로세스에 수반하기로 결정한 것을 기준으로 사용자에게 한 단계 또는 다단계 인증(SFA 또는 MFA)을 제공하라는 메시지가 표시됩니다.

- 사용자가 도메인에 가입된 컴퓨터에 로그인한 경우 Teams를 시작할 때 조직에서 MFA 필요 여부 또는 컴퓨터에서 이미 MFA에 로그인해야 하는지 여부에 따라 인증 단계를 한 번 더 수행하라는 메시지가 표시될 수 있습니다. 컴퓨터에서 이미 MFA에 로그인해야 하는 경우 Teams를 열면 앱이 자동으로 시작됩니다.

- **사용자가 도메인에 가입된 컴퓨터에 로그인하고 사용자 이름이 Teams 로그인 화면**에 미리 채워지지 않도록 하려면 관리자가 다음 Windows 레지스트리를 설정하여 UPN(사용자 이름의 사전 채우기)를 해제할 수 있습니다.

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > ".local" 또는 ".corp"로 끝나는 사용자 이름에 대한 사용자 이름 미리 채우기를 건너뛰거나 무시하는 것이 기본적으로 설정되어 있으므로 이를 끄려고 레지스트리 키를 설정하지 않아도 됩니다. 


### <a name="mac-users"></a>Mac 사용자 

사용자가 Teams 시작할 때 해당 컴퓨터는 Office 365 Enterprise 계정 또는 기타 Office 응용 프로그램에서 자격 증명을 가져올 수 없습니다. 대신 조직 설정에 따라 SFA나 MFA에 대해 묻는 메시지가 표시됩니다. 사용자가 자격 증명을 입력한 후에는 다시 제공할 필요가 없습니다. 이때부터 Teams가 같은 컴퓨터에서 작업하는 경우 자동으로 시작됩니다.

## <a name="switching-accounts-after-completing-modern-authentication"></a>최신 인증을 완료한 후 계정 전환

사용자가 도메인에 가입된 컴퓨터에서 작업하는 경우(예: 테넌트에 Kerberos가 설정된 경우) 최신 인증을 완료한 후에는 사용자 계정을 전환할 수 없습니다. 도메인에 가입된 컴퓨터에서 사용자가 작업하지 않는 경우 계정을 전환할 수 있습니다.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>최신 인증을 완료한 후 Teams에서 로그아웃
Teams에서 로그아웃하려면 사용자가 앱 맨 위에 있는 프로필 사진을 클릭한 다음 **로그아웃**을 선택하면 됩니다. 작업 표시줄에서 앱 아이콘을 마우스 오른쪽 단추로 클릭한 다음 **로그아웃**을 선택할 수도 있습니다. Teams에서 로그아웃한 후에는 해당 사용자의 자격 증명을 다시 입력하여 앱을 시작해야 합니다.

## <a name="urls-and-ip-address-ranges"></a>URL 및 IP 주소 범위
Teams를 사용하려면 인터넷에 연결되어 있어야 합니다. Office 365 요금제, 정부 및 기타 클라우드에서 Teams를 사용하는 고객이 도달할 수 있는 끝점을 이해하려면 [Office 365 URL 및 IP 주소 범위 ](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)를 읽어보세요. 

> [!IMPORTANT]
> 현재 Teams는 모든 사용자에 대해 Google ssl.gstatic.com 서비스에 대한 액세스(TCP 포트 443)가 필요합니다(모든 사용자를 위한 https://ssl.gstatic.com). Gstatic을 사용하지 않는 경우에도 마찬가지입니다). Teams에서 이 요구 사항은 곧 제거됩니다(2020 초). 이 문서를 해당 시점에 업데이트하겠습니다.

## <a name="troubleshooting-modern-authentication"></a>최신 인증 문제 해결

최신 인증은 Teams를 사용하는 모든 조직에서 사용할 수 있으므로 사용자가 프로세스를 완료할 수 없는 경우 도메인 또는 조직의 Office 365 Enterprise 계정에 문제가 있을 수 있습니다. 

자세한 내용은 [왜 Microsoft Teams에 로그인하는 데 문제가 있나요?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)를 참조하세요.

