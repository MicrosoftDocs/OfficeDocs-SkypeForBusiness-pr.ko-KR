---
title: 비즈니스용 Skype 서버에서 외부 사용자에 대 한 보관 부인 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: '요약: 비즈니스용 Skype 서버에 대 한 보관 거부를 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: 86430ac80d85ed166ae091119f4261cdc5e1ff9b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188475"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="c49ec-103">비즈니스용 Skype 서버에서 외부 사용자에 대 한 보관 부인 구성</span><span class="sxs-lookup"><span data-stu-id="c49ec-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="c49ec-104">**요약:** 비즈니스용 Skype 서버용 보관 고 지 사항 구성 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c49ec-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="c49ec-105">조직이 외부 파트너와 통신 하는 경우에는 사용자가 통신을 보관 하 고 있다는 것을 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="c49ec-106">Edge 서버를 배포 하 고 조직에 대해 페더레이션을 사용 하는 경우 외부 파트너에 게 자동으로 보관 거부를 보낼지 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="c49ec-107">이 구성을 변경 해야 하는 경우 비즈니스용 Skype 서버 제어판 또는 Windows PowerShell **CsAccessEdgeConfiguration** cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="c49ec-108">Cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="c49ec-109">외부 사용자가 비즈니스용 Skype 서버 배포에서 사용자와 공동 작업할 수 있도록 하려면 외부 사용자 액세스를 지원 하기 위해 하나 이상의 외부 액세스 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="c49ec-110">자세한 내용은 조직의 XMPP 페더레이션 파트너 관리를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c49ec-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="c49ec-111">특정 페더레이션 도메인에 대 한 액세스 제어에 대 한 자세한 내용은 개별 페더레이션 도메인에의 한 액세스 제어를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c49ec-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="c49ec-112">제어판을 사용 하 여 보관 고 지 사항 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c49ec-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="c49ec-113">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c49ec-114">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c49ec-115">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **액세스 경계 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="c49ec-116">**액세스 경계 구성** 탭에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c49ec-117">**액세스에 지 구성 편집**의 **페더레이션 및 공용 IM 연결을 사용 하도록 설정**하 고, 자동으로 보관을 설정 하거나 해제 하려면 페더레이션 **파트너에 게 보관 고 지 사항 보내기** 확인란을 선택 하거나 선택을 취소 합니다. 고 지 사항.</span><span class="sxs-lookup"><span data-stu-id="c49ec-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="c49ec-118">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="c49ec-119">Windows PowerShell을 사용 하 여 보관 거부 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c49ec-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="c49ec-120">보관 부인를 사용 하도록 설정 하려면 **EnableArchivingDisclaimer** 속성 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="c49ec-121">보관 고 지 사항을 사용 하지 않으려면 **EnableArchivingDisclaimer** 속성 값을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c49ec-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


