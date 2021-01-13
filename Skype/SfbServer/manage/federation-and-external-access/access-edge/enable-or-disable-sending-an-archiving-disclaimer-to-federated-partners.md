---
title: 페더레이션 파트너로 보관 고지 사항 보내기를 사용하도록 설정 또는 해제
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 1f0238e177e74dc1263208f9a6a350158825d825
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817358"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="933c1-102">비즈니스용 Skype 서버에서 페더링 파트너에게 보관 고지 조항 보내기 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="933c1-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="933c1-p101">에지 서버를 배포하고 조직에 대해 페더레이션을 사용하도록 설정할 때 보관 고지 사항을 페더레이션 파트너에게 자동으로 보낼지 여부를 지정해야 합니다. 외부 통신을 보관할 경우에는 보관 고지 사항을 보낼 수 있도록 설정해야 합니다 해당 구성을 변경하려면 이 항목의 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners. If you archive external communications, you should enable the sending of an archiving disclaimer. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="933c1-106">다음 절차에서는 이미 조직에 대해 페더레이션이 사용하도록 설정되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="933c1-107">페더링을 사용하도록 설정하는 데 대한 자세한 내용은 원격 사용자 액세스 사용 또는 사용 [안 하도록 설정 을 참조합니다.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="933c1-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="933c1-108">페더레이션 파트너에게 보관 고지 사항 보내기를 사용하거나 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="933c1-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="933c1-109">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="933c1-110">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="933c1-111">왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭한 다음 **액세스 에지 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="933c1-112">**액세스 에지 구성** 탭에서 **전역**, **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="933c1-113">**액세스 에지 구성 편집** 의 **페더레이션 사용자와의 통신 사용** 에서 **페더레이션 파트너에게 보관 고지 사항 보내기** 확인란을 선택하거나 선택 취소하여 보관 고지 사항을 자동으로 보내거나 보내지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="933c1-114">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-114">Click **Commit**.</span></span>

<span data-ttu-id="933c1-115">페더러가 비즈니스용 Skype 서버 배포에서 사용자와 공동 작업을 할 수 있도록 페더러가 사용자 액세스를 지원하도록 하나 이상의 외부 액세스 정책도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="933c1-116">특정 페더링 도메인에 대한 액세스를 제어하는 데 대한 자세한 내용은 허용되는 외부 도메인에 대한 지원 [구성을 참조합니다.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="933c1-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="933c1-117">cmdlet을 사용하여 보관 고지 Windows PowerShell 사용 안</span><span class="sxs-lookup"><span data-stu-id="933c1-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="933c1-118">보관 고지 조항의 사용은 Windows PowerShell cmdlet을 사용하여 관리할 Set-CsAccessEdgeConfiguration 있습니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="933c1-119">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="933c1-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="933c1-120">보관 고지 조항을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="933c1-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="933c1-121">보관 고지 사항을 사용하도록 설정하려면 **EnableArchivingDisclaimer** 속성 값을 True($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="933c1-122">보관 고지 조항을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="933c1-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="933c1-123">보관 고지 사항을 사용하지 않도록 설정하려면 **EnableArchivingDisclaimer** 속성 값을 False($False)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="933c1-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


