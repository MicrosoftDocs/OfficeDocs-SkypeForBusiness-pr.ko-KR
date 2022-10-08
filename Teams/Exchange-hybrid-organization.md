---
title: Exchange 하이브리드 조직 구성
author: JoanneHendrickson
ms.author: jhendr
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
description: 그룹 멤버 자격이 동기화되도록 Microsoft Teams와 함께 사용할 Exchange 하이브리드 조직을 구성하는 방법을 알아봅니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cb2471a2680218a69daa74d20b27c4b7642fa1d7
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480678"
---
# <a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Microsoft Teams에서 사용할 Exchange 하이브리드 조직 구성

일반적으로 Microsoft Teams에서 사용할 Exchange Online 기능을 구성할 필요가 없습니다. 그러나 Exchange 하이브리드 시나리오의 경우 그룹 멤버 자격이 Exchange Server(온-프레미스)와 Exchange Online 간에 동기화되도록 하는 데 필요한 단계가 있습니다. 여기에는 다양한 초기화 스크립트와 함께 Azure AD Connect에서 그룹 쓰기 저장 기능을 사용하도록 설정하는 작업이 포함[됩니다. 온-프레미스 Exchange 하이브리드를 사용하여 Microsoft 365 그룹 구성](/exchange/hybrid-deployment/set-up-microsoft-365-groups)합니다.