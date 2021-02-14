---
title: Exchange 하이브리드 조직 구성
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 그룹 멤버 자격이 동기화되도록 Microsoft Teams에서 사용할 Exchange 하이브리드 조직을 구성하는 방법을 배워야 합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1061ce633dcd1db8f956a37143850deed9855e56
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46551964"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Microsoft Teams에서 사용할 Exchange 하이브리드 조직 구성
======================================================================

일반적으로 Microsoft Teams에서 사용할 Exchange Online 기능을 구성할 필요가 없습니다. 그러나 Exchange 하이브리드 시나리오의 경우 그룹 멤버 자격이 Exchange Server(프레미스)와 Exchange Online 간에 동기화되도록 하는 데 필요한 단계가 있습니다. 여기에는 다양한 초기화 스크립트와 함께 Azure AD Connect에서 그룹 쓰기 쓰기 저장소 기능을 사용하도록 설정해야 [합니다. 즉, Microsoft 365 그룹](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups)구성이 프레미스 Exchange 하이브리드로 구성됩니다.
