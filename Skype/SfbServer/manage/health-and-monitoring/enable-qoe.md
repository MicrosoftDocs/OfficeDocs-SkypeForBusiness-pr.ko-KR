---
title: 비즈니스용 Skype 서버에서 환경 품질 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: '요약: 비즈니스용 Skype 서버에서 환경 품질 (체감 품질)을 사용 하도록 설정 하는 방법을 알아봅니다.'
ms.openlocfilehash: 0a05266ed88b9d476ca787f1d32b91727e90475c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992938"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="30339-103">비즈니스용 Skype 서버에서 환경 품질 사용</span><span class="sxs-lookup"><span data-stu-id="30339-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="30339-104">**요약:** 비즈니스용 Skype 서버에서 환경 품질 (체감 품질)을 사용 하도록 설정 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="30339-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="30339-105">환경 품질 (체감 품질)은 통화 및 세션과 관련 된 참가자, 장치 이름, 드라이버, IP 주소, 끝점 형식에 대 한 미디어 품질과 정보를 표시 하는 숫자 데이터를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="30339-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="30339-106">자세한 내용은 계획 설명서의 [모니터링 계획](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30339-106">For details, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="30339-107">조직의 전체 조직 또는 각 사이트에 대해 체감 품질을 사용 하도록 설정 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="30339-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="30339-108">체감 품질을 사용 하도록 설정 하려면 먼저 모니터링과 모니터링 백 엔드 데이터베이스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30339-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="30339-109">자세한 내용은 [모니터링 배포](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30339-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="30339-110">비즈니스용 Skype 서버 제어판을 사용 하 여 체감 품질을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="30339-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="30339-111">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="30339-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="30339-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="30339-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="30339-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30339-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="30339-114">**경력 데이터** 페이지에서 테이블의 적절 한 컬렉션을 클릭 하 고 **작업**을 클릭 한 다음 **체감 품질 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30339-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="30339-115">Windows PowerShell Cmdlet을 사용 하 여 체감 품질 사용</span><span class="sxs-lookup"><span data-stu-id="30339-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="30339-116">Windows PowerShell 및 **Set-CsQoEConfiguration** cmdlet을 사용 하 여 체감 품질를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30339-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="30339-117">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30339-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="30339-118">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30339-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="30339-119">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="30339-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="30339-120">단일 위치에 대해 체감 품질을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="30339-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="30339-121">체감 품질을 사용 하도록 설정 하려면 EnableQoE 매개 변수를 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="30339-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="30339-122">단일 위치에 대해 체감 품질를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="30339-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="30339-123">체감 품질를 사용 하지 않으려면 EnableQoE 매개 변수를 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="30339-123">To disable QoE, set the EnableQoE parameter to False ($False).</span></span> <span data-ttu-id="30339-124">이는 모니터링을 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30339-124">This does not uninstall monitoring.</span></span> <span data-ttu-id="30339-125">체감 품질 데이터의 컬렉션 및 저장소를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="30339-125">It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="30339-126">단일 명령을 사용 하 여 여러 위치에서 체감 품질을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="30339-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="30339-127">이 명령은 현재 조직에서 사용 중인 모든 체감 품질 구성 설정에 대해 체감 품질을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="30339-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="30339-128">자세한 내용은 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30339-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="30339-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30339-129">See also</span></span>

[<span data-ttu-id="30339-130">모니터링 계획</span><span class="sxs-lookup"><span data-stu-id="30339-130">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="30339-131">모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="30339-131">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

