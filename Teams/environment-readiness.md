---
title: Microsoft 팀에 대 한 환경의 준비 상태 확인
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dansteve
description: Microsoft 팀에 대 한 환경의 준비 상태를 확인할 때 알아 볼 수 있습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 48af92d4e7a325fdcabd1650b987a12bfb1ddf50
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832868"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>Microsoft 팀에 대 한 환경의 준비 상태 확인
===========================================

클라우드로의 전환은 각 조직에 따라 달라 지지만 현재 상태는 팀이 작동 하는 방식에 영향을 줄 수 있습니다.

교육 기관은 Microsoft 팀을 배포 하기 전에 [School Data Sync를 배포](https://docs.microsoft.com/schooldatasync/) 하는 것이 좋습니다. School Data Sync에서는 학교의 SIS 명단 데이터를 사용 하 여 Microsoft 팀 및 기타 응용 프로그램에 대 한 수업 및 그룹을 자동으로 만듭니다.

팀에 대 한 최상의 환경을 얻으려면 조직에서 Exchange Online 및 SharePoint Online을 배포 해야 합니다. 또한 현재 환경에서 팀에 대 한 준비가 되었는지 확인 해야 합니다.  다음 링크를 참조 하 여 도움을 받으세요.

-   조직에서 Office 365 작업을 배포 하지 않은 경우 [비즈니스용 office 365 시작](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029) 을 참조 하세요.

-   조직이 Office 365의 확인 된 도메인을 추가 하거나 구성 하지 않은 경우 [office 365 도메인 확인](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)을 참조 하세요.

-   조직이 Azure Active Directory와 id를 동기화 하지 않은 경우 [Microsoft 팀의 id 모델 및 인증](identify-models-authentication.md)을 참조 하세요.

-   조직에 Exchange Online이 없는 경우 [exchange 및 Microsoft 팀의 상호 작용 방법 이해](Exchange-Teams-interact.md)를 참조 하세요.

-   조직에 SharePoint Online이 없는 경우 [Sharepoint online 및 비즈니스용 OneDrive에서 Microsoft 팀과 상호 작용 하는 방법 이해](SharePoint-OneDrive-interact.md)를 참조 하세요.

- 조직이 교육 기관이 고 SIS (학생 정보 시스템)를 사용 하는 경우 Microsoft 팀을 배포 하기 전에 [School Data Sync를 배포](https://docs.microsoft.com/schooldatasync/) 합니다.

- 조직에 기존 온-프레미스 비즈니스용 Skype 서버 (또는 Lync Server) 배포를 사용 하는 경우 Azure AD Connect를 구성 하 여 온-프레미스 디렉터리를 Office 365와 동기화 해야 합니다.  자세한 내용은 [팀 및 비즈니스용 Skype에 대 한 AZURE AD Connect 구성을](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect)참조 하세요.