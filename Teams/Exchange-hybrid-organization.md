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
description: Microsoft Teams와 함께 사용할 Exchange 하이브리드 조직을 구성하여 그룹 멤버 자격이 동기화되도록 하는 방법을 알아보습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90250b3d3f3593990d356843bebea324060d6f8b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094610"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="dde40-103">Microsoft Teams에서 사용할 Exchange 하이브리드 조직 구성</span><span class="sxs-lookup"><span data-stu-id="dde40-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="dde40-104">일반적으로 Microsoft Teams에서 사용할 Exchange Online 기능을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dde40-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="dde40-105">그러나 Exchange Hybrid 시나리오의 경우 그룹 멤버 자격이 온라인(Exchange Server)과 Exchange Online 간에 동기화되도록 하는 데 필요한 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dde40-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="dde40-106">여기에는 다양한 초기화 스크립트와 함께 Azure AD Connect에서 그룹 쓰기 저장소 기능을 사용하도록 설정해야 합니다. 즉, Microsoft 365 그룹 구성 및 [On-프레미스 Exchange 하이브리드가 있습니다.](/exchange/hybrid-deployment/set-up-microsoft-365-groups)</span><span class="sxs-lookup"><span data-stu-id="dde40-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups).</span></span>