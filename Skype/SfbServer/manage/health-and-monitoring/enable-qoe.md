---
title: 비즈니스용 Skype 서버에서 환경 품질 사용
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: '요약: 비즈니스용 Skype 서버에서 QoE(QoE)를 사용하도록 설정하는 방법을 학습합니다.'
ms.openlocfilehash: 9f3e032506641cd22fbaa78054fcf6e40a72665e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095212"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="c8572-103">비즈니스용 Skype 서버에서 환경 품질 사용</span><span class="sxs-lookup"><span data-stu-id="c8572-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="c8572-104">**요약:** 비즈니스용 Skype 서버에서 QoE(QoE)를 사용하도록 설정하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="c8572-105">QoE(체감 품질)는 통화 및 세션에 포함된 참가자, 장치 이름, 드라이버, IP 주소, 끝점 유형에 대한 정보 및 미디어의 품질을 나타내는 숫자 데이터를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="c8572-106">자세한 내용은 계획 설명서에서 [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8572-106">For details, see [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation.</span></span>

<span data-ttu-id="c8572-107">다음 절차를 사용하여 전체 조직이나 조직의 각 사이트에 대해 QoE를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="c8572-108">QoE를 사용하도록 설정하려면 먼저 모니터링 및 모니터링 백 엔드 데이터베이스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="c8572-109">자세한 내용은 [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8572-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c8572-110">비즈니스용 Skype 서버 제어판을 사용하여 QoE를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c8572-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c8572-111">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="c8572-112">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="c8572-113">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **체감 품질 데이터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="c8572-114">**체감 품질 데이터** 페이지의 테이블에서 적합한 컬렉션을 클릭하고 **동작**, **QoE 사용** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c8572-115">Cmdlet을 사용하여 QoE Windows PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="c8572-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c8572-116">**Set-CsQoEConfiguration** cmdlet과 set-Windows PowerShell 사용하여 QoE를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="c8572-117">비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 이 cmdlet을 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8572-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c8572-118">원격 Windows PowerShell 사용하여 비즈니스용 Skype 서버에 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="c8572-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c8572-119">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="c8572-120">단일 위치에서 QoE를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c8572-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="c8572-121">QoE를 사용하도록 설정하려면 EnableQoE 매개 변수를 True($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="c8572-122">단일 위치에서 QoE를 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c8572-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="c8572-p104">QoE를 사용하지 않도록 설정하려면 EnableQoE 매개 변수를 False($False)로 설정합니다. 이 경우 모니터링이 제거되지는 않습니다. 다만 컬렉션과 QoE 데이터 저장소가 일시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="c8572-126">단일 명령을 사용하여 여러 위치에서 QoE를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c8572-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="c8572-127">다음 명령을 사용하면 조직에서 현재 사용 중인 모든 QoE 구성 설정에 대해 QoE를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8572-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="c8572-128">자세한 내용은 [Set-CsQoEConfiguration을 참조합니다.](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c8572-128">For details, see [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8572-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8572-129">See also</span></span>

[<span data-ttu-id="c8572-130">모니터링 계획</span><span class="sxs-lookup"><span data-stu-id="c8572-130">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="c8572-131">모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="c8572-131">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)