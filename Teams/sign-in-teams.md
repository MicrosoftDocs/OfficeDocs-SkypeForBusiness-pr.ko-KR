---
title: 최신 인증을 사용 하 여 Microsoft 팀에 로그인
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 최신 인증을 사용 하 여 Microsoft 팀에 로그인 하는 방법
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dc79f6913a2996734b34d589f124c440eb9835e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "36180693"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>최신 인증을 사용 하 여 Microsoft 팀에 로그인
==========================

Microsoft 팀은 최신 인증을 사용 하 여 로그인 환경을 간단 하 고 안전 하 게 유지 합니다. 사용자가 팀에 로그인 하는 방법을 보려면 [팀에 로그인](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)을 읽어보십시오.

## <a name="how-modern-authentication-works"></a>최신 인증이 작동 하는 방식

최신 인증은 사용자가 이미 자신의 자격 증명 (예: 회사 전자 메일 및 암호)을 입력 하 고 앱을 시작 하기 위해 다시 입력할 필요가 없다는 것을 팀에서 알 수 있도록 하는 프로세스입니다. 환경은 사용자가 Windows 또는 Mac에서 작업 하는 경우와 같은 몇 가지 요인에 따라 달라 집니다. 또한 조직이 단일 요소 인증을 사용 하도록 설정 했는지, 또는 다단계 인증이 일반적으로 휴대폰을 통해 자격 증명 확인, 고유 코드 제공, PIN 입력 등의 작업에 따라 달라 집니다. 지문 발표). 다음은 최신 인증 시나리오의 개요입니다.

### <a name="windows-users"></a>Windows 사용자 

- 사용자가 Office 365 Enterprise 계정을 통해 다른 Office 앱에 이미 로그인 한 경우, 팀을 시작할 때 앱으로 바로 가져올 수 있습니다. 자격 증명을 입력할 필요가 없습니다.

- 사용자가 Office 365 Enterprise 계정에 로그인 되어 있지 않은 경우, 즉 팀을 시작할 때 조직이 다음과 같이 결정 한 사항에 따라 단일 인수 또는 다단계 인증 (SFA 또는 MFA)을 제공 하 라는 메시지가 표시 됩니다. 프로세스를 수반 합니다.

- 사용자가 도메인에 가입한 컴퓨터에 로그인 한 경우 팀을 시작할 때 조직에 MFA가 필요 하거나 컴퓨터에 MFA가 이미 있는지 여부에 따라 인증 단계를 한 번 더 수행 하 라는 메시지가 표시 될 수 있습니다. 컴퓨터에 이미 MFA가 있어야 로그인 하는 경우 팀을 열면 앱이 자동으로 시작 됩니다.

### <a name="mac-users"></a>Mac 사용자 

사용자가 팀을 시작 하면 해당 컴퓨터에서 Office 365 엔터프라이즈 계정 또는 다른 Office 응용 프로그램의 자격 증명을 가져올 수 없습니다. 대신 사용자에 게 해당 조직의 설정에 따라 SFA 나 MFA를 묻는 메시지가 표시 됩니다. 사용자가 자격 증명을 입력 한 후에는 다시 제공 하지 않아도 됩니다. 이 시점부터 팀이 같은 컴퓨터에서 작업 하는 경우 자동으로 시작 됩니다.

## <a name="switching-accounts-after-completing-modern-authentication"></a>최신 인증을 완료 한 후 계정 전환

사용자가 도메인에 가입 된 컴퓨터에서 작업 하는 경우 (예: 테 넌 트가 Kerberos를 사용 하도록 설정한 경우) 사용자 계정이 최신 인증을 완료 한 후에는 전환할 수 없습니다. 도메인에 가입 된 컴퓨터에서 사용자가 작업 하지 않는 경우 계정을 전환할 수 있습니다.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>최신 인증을 완료 한 후 Microsoft 팀에서 로그 아웃
팀에서 로그 아웃 하려면 사용자가 앱 맨 위에 있는 프로필 사진을 클릭 한 다음 **로그 아웃**을 선택 하면 됩니다. 작업 표시줄에서 앱 아이콘을 마우스 오른쪽 단추로 클릭 한 다음 **로그 아웃**을 선택 해도 됩니다. 팀에서 로그 아웃 한 후에는 앱을 실행 하기 위해 자격 증명을 다시 입력 해야 합니다.

## <a name="troubleshooting-modern-authentication"></a>최신 인증 문제 해결

최신 인증은 팀을 사용 하는 모든 조직에서 사용할 수 있으므로 사용자가 프로세스를 완료할 수 없는 경우 도메인 이나 조직의 Office 365 Enterprise 계정에 문제가 있을 수 있습니다. 

자세한 내용은 [Microsoft 팀에 로그인 하는 데 문제가 있는 이유](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)를 참조 하세요.

