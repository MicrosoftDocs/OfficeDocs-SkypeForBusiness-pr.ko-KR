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
description: 그룹 구성원 자격이 동기화 되도록 Microsoft 팀과 함께 사용할 Exchange 하이브리드 조직을 구성 하는 방법에 대해 알아봅니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee558c8c8bfa6c5bd66e001d31ed76a8061df3f4
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902963"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="51177-103">Microsoft 팀과 함께 사용할 Exchange 하이브리드 조직 구성</span><span class="sxs-lookup"><span data-stu-id="51177-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="51177-104">일반적으로 Microsoft 팀에서 사용할 Exchange Online 기능을 구성할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51177-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="51177-105">그러나 Exchange 하이브리드 시나리오의 경우 Exchange Server (온-프레미스)와 Exchange Online 간에 그룹 구성원이 동기화 되도록 하는 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="51177-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="51177-106">여기에는 Azure AD Connect의 그룹 쓰기 되돌림 기능을 사용 하는 경우 다양 한 초기화 스크립트 (온 [-프레미스 Exchange 하이브리드을 사용 하 여 Microsoft 365 그룹 구성)](https://go.microsoft.com/fwlink/?linkid=854389)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51177-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
