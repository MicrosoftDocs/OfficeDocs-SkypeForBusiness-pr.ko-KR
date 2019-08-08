---
title: 비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: '요약: 비즈니스용 skype 서버 제어판을 사용 하 여 비즈니스용 Skype 서버에서 음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 6a13c2a2b2b1221203fbed84948b803a6c2ea1db
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240194"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="f7f65-103">비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="f7f65-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="f7f65-104">**요약:** 비즈니스용 skype 서버 제어판을 사용 하 여 비즈니스용 Skype 서버에서 음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="f7f65-105">**음성 라우팅** 그룹의 페이지에서 구성 설정을 변경한 후에는이 절차를 수행 하 여 보류 중인 변경 내용을 검토 하거나 게시 하거나 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f7f65-106">한 번에 한 명의 사용자만 음성 라우팅 구성 설정을 수정 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f7f65-107">보류 중인 모든 변경 내용은 **모두 커밋** 명령을 실행 하 여 동시에 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-107">All pending changes must be published at the same time by running the **Commit all** command.</span></span> <span data-ttu-id="f7f65-108">보류 중인 변경 내용을 선택적으로 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-108">You cannot selectively publish pending changes.</span></span> <span data-ttu-id="f7f65-109">보류 중인 변경 내용을 게시 하기 전에 **커밋되지 않은 변경 내용 검토** 명령을 실행 하 고 게시 하지 않으려는 구성 변경 내용을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-109">Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f7f65-110">보류 중인 변경 내용을 커밋하기 전에 **음성 라우팅** 그룹의 페이지에서 다른 위치로 이동 하면 보류 중인 변경 내용이 모두 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="f7f65-111">그러나 보류 중인 변경 내용을 포함 하 여 현재 구성을 음성 구성 파일로 내보낸 다음 업데이트 된 구성을 가져오고 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="f7f65-112">자세한 내용은 [비즈니스용 Skype에서 음성 경로 구성 파일 내보내기 또는 가져오기를](voice-route-configuration-import-export.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7f65-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="f7f65-113">음성 라우팅 구성 변경 내용을 검토, 게시 또는 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="f7f65-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="f7f65-114">RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="f7f65-115">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f7f65-116">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="f7f65-117">**음성 라우팅** 그룹의 각 페이지에 대 한 설정을 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="f7f65-118">보류 중인 변경 내용을 게시 하지 않고 검토 하려면 **커밋** 메뉴에서 **커밋되지 않은 변경 내용 검토** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="f7f65-119">보류 중인 변경 내용을 취소 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="f7f65-120">**커밋** 메뉴에서 **커밋되지 않은 변경 내용 모두 취소** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="f7f65-121">취소 하려는 보류 중인 변경 내용이 있는 **음성 라우팅** 페이지의 탭으로 이동 하 고 보류 중인 변경 내용이 있는 항목을 선택한 다음 **커밋을**클릭 하 고 **선택한 변경 내용 취소**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="f7f65-122">보류 중인 변경 내용을 모두 검토 하 고 게시 하지 않으려는 작업을 취소 한 후에는 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="f7f65-123">모든 보류 중인 변경 내용 목록을 표시 하는 **커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="f7f65-124">비즈니스용 Skype Server 제어판에서 변경 내용이 커밋되면 **성공적으로 게시 된 음성 라우팅 구성** 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f7f65-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

