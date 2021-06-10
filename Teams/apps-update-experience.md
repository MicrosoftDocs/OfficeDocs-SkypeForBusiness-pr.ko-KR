---
title: 앱 업데이트 환경 Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 앱에서 앱을 업데이트하는 Microsoft Teams.
ms.openlocfilehash: b39b831b644b19038b8f4574acf3e5bc5c50d73c
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337832"
---
# <a name="update-apps-in-microsoft-teams"></a><span data-ttu-id="55a4c-103">앱 업데이트 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55a4c-103">Update apps in Microsoft Teams</span></span>

<span data-ttu-id="55a4c-104">대부분의 경우 앱 개발자가 앱 업데이트를 게시하면 새 버전이 사용자에게 자동으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="55a4c-104">In most cases, after app developers publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="55a4c-105">그러나 사용자 수락을 <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank"></a> 완료해야 하는 Microsoft Teams 매니페스트에 대한 몇 가지 업데이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55a4c-105">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="55a4c-106">봇이 추가되거나 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55a4c-106">A bot was added or removed</span></span>
* <span data-ttu-id="55a4c-107">기존 봇의 "botId" 속성이 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="55a4c-107">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="55a4c-108">기존 봇의 "isNotificationOnly" 속성이 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="55a4c-108">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="55a4c-109">봇의 "supportsFiles" 속성이 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="55a4c-109">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="55a4c-110">메시징 확장이 추가되거나 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55a4c-110">A messaging extension was added or removed</span></span>
* <span data-ttu-id="55a4c-111">새 커넥터가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55a4c-111">A new connector was added</span></span>
* <span data-ttu-id="55a4c-112">새 정적 탭이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55a4c-112">A new static tab was added</span></span>
* <span data-ttu-id="55a4c-113">새 구성 가능한 탭이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55a4c-113">A new configurable tab was added</span></span>
* <span data-ttu-id="55a4c-114">"webApplicationInfo" 내부 속성이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55a4c-114">Properties inside "webApplicationInfo" changed</span></span>

![새 버전 사용 가능](media/manage-your-custom-apps-update1.png)

![앱의 업그레이드 옵션](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> <span data-ttu-id="55a4c-117">업데이트 프로세스는 Microsoft 앱, 사용자 지정 앱 및 타사 앱에 대한 모든 앱 업데이트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55a4c-117">The update process applies to all app updates for Microsoft apps, custom apps, and third-party apps.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="55a4c-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="55a4c-118">Related topics</span></span>

[<span data-ttu-id="55a4c-119">앱 관리</span><span class="sxs-lookup"><span data-stu-id="55a4c-119">Manage apps</span></span>](manage-apps.md)