---
title: Microsoft 팀과 함께 사용할 Exchange 하이브리드 조직 구성
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Microsoft 팀과 함께 사용할 Exchange 하이브리드 조직을 구성 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68b2fee13668db8ba3986302d58bc16b0fa89080
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235464"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Microsoft 팀과 함께 사용할 Exchange 하이브리드 조직 구성
======================================================================

일반적으로 Microsoft 팀에서 사용할 Exchange Online 기능을 구성할 필요는 없습니다. 그러나 Exchange 하이브리드 시나리오의 경우 Exchange Server (온-프레미스)와 Exchange Online 간에 그룹 구성원이 동기화 되도록 하는 단계가 필요 합니다. 여기에는 Azure AD Connect의 그룹 쓰기 되돌림 기능을 사용 하는 경우 다양 한 초기화 스크립트 (온 [-프레미스 Exchange 하이브리드을 사용 하 여 Office 365 그룹 구성)](https://go.microsoft.com/fwlink/?linkid=854389)가 포함 됩니다.
