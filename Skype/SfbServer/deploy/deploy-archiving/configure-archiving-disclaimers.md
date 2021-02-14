---
title: 비즈니스용 Skype 서버에서 외부 사용자에 대한 보관 고지 조항 구성
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
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버에 대한 보관 고지 사항 구성 방법을 배워야 합니다.'
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820668"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="20ec1-103">비즈니스용 Skype 서버에서 외부 사용자에 대한 보관 고지 조항 구성</span><span class="sxs-lookup"><span data-stu-id="20ec1-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="20ec1-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버에 대한 보관 고지 조항을 구성하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="20ec1-105">조직이 외부 파트너와 통신하는 경우 해당 파트너와의 통신을 보관하고 있는 것을 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="20ec1-106">에지 서버를 배포하고 조직에 대해 페더링을 사용하도록 설정하는 경우 보관 고지 조항을 외부 파트너에게 자동으로 보낼지 여부를 묻는 메시지를 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="20ec1-107">이 구성을 변경해야 하는 경우 비즈니스용 Skype 서버 제어판 또는 **Set-CsAccessEdgeConfiguration** cmdlet을 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="20ec1-108">Cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버의 원격 세션에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20ec1-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="20ec1-109">외부 사용자가 비즈니스용 Skype 서버 배포에서 사용자와 공동 작업을 할 수 있도록 설정하려면 외부 사용자 액세스를 지원하도록 하나 이상의 외부 액세스 정책도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="20ec1-110">자세한 내용은 조직에 대한 XMPP 페더리트 파트너 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20ec1-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="20ec1-111">특정 페더링 도메인에 대한 액세스를 제어하는 데 대한 자세한 내용은 개별 페더링 도메인의 액세스 제어를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="20ec1-112">제어판을 사용하여 보관 고지 조항 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="20ec1-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="20ec1-113">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="20ec1-114">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="20ec1-115">왼쪽 탐색 모음에서 연결 및 외부 액세스를 클릭한 다음 **액세스 에지 구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="20ec1-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="20ec1-116">**액세스 에지 구성** 탭에서 **전역**, **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="20ec1-117">액세스 에지 구성 편집의 페더링 및 공용 **IM** 연결  사용에서 페더링 파트너에 대한 보관 고지 조항 보내기 확인란을 선택하거나 선택 취소하여 보관 고지 조항을 자동으로 보내거나 보내지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="20ec1-118">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="20ec1-119">보관 고지 조항을 사용하여 보관 고지 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20ec1-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="20ec1-120">보관 고지 사항을 사용하도록 설정하려면 **EnableArchivingDisclaimer** 속성 값을 True($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="20ec1-121">보관 고지 사항을 사용하지 않도록 설정하려면 **EnableArchivingDisclaimer** 속성 값을 False($False)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="20ec1-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


