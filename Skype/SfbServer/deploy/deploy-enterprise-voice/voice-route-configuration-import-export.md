---
title: 비즈니스용 Skype에서 음성 경로 구성 파일 내보내기 또는 가져오기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '요약: 비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버에서 음성 라우팅 구성 파일을 내보내거나 가져오는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830358"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="8b150-103">비즈니스용 Skype에서 음성 경로 구성 파일 내보내기 또는 가져오기</span><span class="sxs-lookup"><span data-stu-id="8b150-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="8b150-104">**요약:** 비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버에서 음성 라우팅 구성 파일을 내보내거나 가져오는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="8b150-105">음성 라우팅 구성을 게시하지 않고 저장하려면 다음 단계에 따라 음성 라우팅 구성의 스냅숏을 저장하고 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="8b150-106">음성 라우팅 구성 파일(.vcfg)을 가져오지만 그동안 서버의 음성 라우팅 구성이 변경된 경우 비즈니스용  Skype 서버 제어판의 음성 라우팅 그룹에 있는 페이지에 음성 라우팅에 커밋되지 않은 변경 내용이 있는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="8b150-107">커밋되지 않은 이러한 변경 내용으로 인해 두 구성 간 차이가 발생하며, 이러한 차이를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="8b150-108">그룹 내의 모든 페이지에서 설정을 커밋하지 않은 변경한 경우 변경 내용은 내보낼 음성 구성 파일(.vcfg)에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="8b150-109">따라서 변경 내용을 게시하기 전에 여러 세션 동안 음성 라우팅 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="8b150-110">음성 라우팅 구성을 내보내려면</span><span class="sxs-lookup"><span data-stu-id="8b150-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="8b150-111">RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator,** **CsServerAdministrator 또는 CsAdministrator** 관리  역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="8b150-112">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8b150-113">왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="8b150-114">**동작** 메뉴에서 **구성 내보내기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="8b150-115">위치 및 파일 이름을 지정하고 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="8b150-116">음성 라우팅 구성을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="8b150-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="8b150-117">RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator,** **CsServerAdministrator 또는 CsAdministrator** 관리  역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="8b150-118">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8b150-119">왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="8b150-120">**동작** 메뉴에서 **구성 가져오기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="8b150-121">가져올 구성 파일을 찾아 **열기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="8b150-122">**커밋**, **모두 커밋** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8b150-123">음성 구성 파일을 가져올 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b150-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="8b150-124">자세한 내용은 작업 설명서에서 비즈니스용 [Skype의](voice-route-config-changes.md) 음성 라우팅 구성에 보류 중인 변경 내용 게시를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b150-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

