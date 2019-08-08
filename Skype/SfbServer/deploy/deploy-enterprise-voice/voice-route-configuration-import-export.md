---
title: 비즈니스용 Skype에서 음성 경로 구성 파일 내보내기 또는 가져오기
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '요약: 비즈니스용 skype 서버 제어판을 사용 하 여 비즈니스용 Skype 서버에서 음성 라우팅 구성 파일을 내보내거나 가져오는 방법에 대해 알아봅니다.'
ms.openlocfilehash: ec5a3d0c7f14d85a7b64eaad1edc73ebe4e24cd2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240171"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="cd644-103">비즈니스용 Skype에서 음성 경로 구성 파일 내보내기 또는 가져오기</span><span class="sxs-lookup"><span data-stu-id="cd644-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="cd644-104">**요약:** 비즈니스용 skype 서버 제어판을 사용 하 여 비즈니스용 Skype 서버에서 음성 라우팅 구성 파일을 내보내거나 가져오는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="cd644-105">음성 라우팅 구성을 게시 하지 않고 저장 하려는 경우 다음 단계에 따라 음성 라우팅 구성의 스냅숏을 저장 하 고 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="cd644-106">음성 라우팅 구성 파일 (vcfg)을 가져올 때, 그 동안 서버의 음성 라우팅 구성이 변경 된 경우 비즈니스용 Skype Server 제어판의 **음성 라우팅** 그룹에 있는 페이지에 있는 것을 표시 합니다. 음성 라우팅의 커밋되지 않은 변경 내용이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="cd644-107">커밋되지 않은 변경 내용은 조정을 필요로 하는 두 구성의 차이점입니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="cd644-108">그룹 내의 모든 페이지에서 설정에 대 한 커밋되지 않은 변경 내용이 있는 경우 해당 변경 내용이 내보낸 음성 구성 파일 (vcfg)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="cd644-109">이렇게 하면 변경 내용을 게시 하기 전에 여러 세션 중에 음성 라우팅 구성 변경을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="cd644-110">음성 라우팅 구성을 내보내려면</span><span class="sxs-lookup"><span data-stu-id="cd644-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="cd644-111">RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="cd644-112">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="cd644-113">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="cd644-114">**작업** 메뉴에서 **구성 내보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="cd644-115">위치 및 파일 이름을 지정한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="cd644-116">음성 라우팅 구성을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="cd644-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="cd644-117">RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="cd644-118">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="cd644-119">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="cd644-120">**작업** 메뉴에서 **구성 가져오기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="cd644-121">가져올 구성 파일을 찾은 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="cd644-122">**커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cd644-123">음성 구성 파일을 가져올 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd644-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="cd644-124">자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd644-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

