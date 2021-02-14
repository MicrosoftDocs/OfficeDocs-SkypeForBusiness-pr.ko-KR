---
title: 비즈니스용 Skype의 통화 파크 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 비즈니스용 Skype 서버 Enterprise Voice 통화를 보류하고 부서로 통화를 전송할 수 있는 통화 파킹 계획 용량 계획, 지원되는 통화 및 지원되는 클라이언트를 포함합니다.
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825928"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="d1c5d-104">비즈니스용 Skype의 통화 파크 계획</span><span class="sxs-lookup"><span data-stu-id="d1c5d-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="d1c5d-105">비즈니스용 Skype 서버 Enterprise Voice 통화를 보류하고 부서로 통화를 전송할 수 있는 통화 파킹 계획</span><span class="sxs-lookup"><span data-stu-id="d1c5d-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="d1c5d-106">용량 계획, 지원되는 통화 및 지원되는 클라이언트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="d1c5d-107">통화 파크 응용 프로그램을 Enterprise Voice 사용자가 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="d1c5d-108">통화를 대기시킨 후에 같은 전화기 또는 다른 전화기에서 통화 재개</span><span class="sxs-lookup"><span data-stu-id="d1c5d-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="d1c5d-109">통화를 대기시키고 이 통화를 특정 부서나 일반 영역(예: 영업 부서 또는 공통 영역 전화가 있는 창고)으로 전송</span><span class="sxs-lookup"><span data-stu-id="d1c5d-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="d1c5d-110">통화를 대기시키고 처음에 응답한 전화기에서 다른 통화 수신</span><span class="sxs-lookup"><span data-stu-id="d1c5d-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="d1c5d-111">사용자가 통화를 파기하면 비즈니스용 Skype 서버가 통화를 파기할 때 통화가 재개되거나 통화가 시간 외일 때까지 통화가 보전되는 파기 번호라는 임시 번호로 통화를 전송합니다. 비즈니스용 Skype 서버가 통화를 시작한 사용자에게 통화 통화를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="d1c5d-112">사용자는 통화 번호로 전화를 걸거나 대화 창에서 파선 링크 또는 단추를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="d1c5d-p104">통화를 대기시킨 사용자는 IM(인스턴트 메시징) 또는 호출 시스템과 같은 외부 메커니즘을 사용하여 파킹된 통화 번호를 전달하는 방식으로 다른 사람에게 통화를 재개하도록 알릴 수 있습니다. 또한 통화를 대기시킨 사용자는 통화가 재개된 경우 알림을 받기 위해 대화 창을 열어 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="d1c5d-115">파킹된 통화 번호 범위는 전역적으로 고유하기 때문에 라우팅이 적절하게 구성된 경우 비즈니스용 Skype 서버 사이트 또는 PBX 전화에서 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="d1c5d-116">구성 가능한 시간 내에 아무도 통화를 재개하지 않으면 통화를 대기시킨 사람에게 통화가 다시 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="d1c5d-117">그런 다음 통화를 대기시킨 사람이 다시 연결된 통화에 응답하지 않으면 통화가 교환원과 같은 대체 대상으로 전송됩니다(이렇게 구성된 경우).</span><span class="sxs-lookup"><span data-stu-id="d1c5d-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="d1c5d-118">이와 같이 통화가 전송되기 전에 통화가 다시 연결되는 횟수(1회~10회)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="d1c5d-119">전송된 통화에 아무도 응답하지 않으면 통화 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="d1c5d-120">통화가 재개되거나 끊긴 경우에는 파킹된 통화 번호가 비워집니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="d1c5d-121">통화 대기를 배포할 때 통화 대기에 사용할 내선 번호(파킹된 통화 번호) 범위를 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="d1c5d-122">이러한 내선 번호는 가상 내선 번호, 즉 할당된 사용자 또는 전화가 없는 내선 번호여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="d1c5d-123">그런 다음 파킹된 통화 번호 범위를 사용하여 통화 대기 파킹된 통화 번호 테이블을 구성하고 각 범위를 처리할 통화 대기 응용 프로그램을 호스팅하는 응용 프로그램 서비스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="d1c5d-124">각 프런트 엔드 풀에는 해당 백 엔드 서버에 풀에서 대기 중인 통화를 관리하는 데 사용되는 통화 대기 테이블이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="d1c5d-125">궤도 범위 목록은 중앙 관리 저장소에 저장되고 궤도는 대상 풀로 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="d1c5d-126">통화 파크 응용 프로그램이 배포 및 구성된 각 비즈니스용 Skype 서버 풀에는 하나 이상의 파인트 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="d1c5d-127">궤도 범위는 비즈니스용 Skype 서버 배포에서 전역적으로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="d1c5d-p107">또한 여러분은 시간 초과된 통화가 리디렉션되는 위치 및 통화 대기 중인 사용자에게 음악을 들려줄지 여부와 같은 다른 통화 대기 설정을 구성할 수 있으며, 통화 대기 중인 동안 재생할 음악 파일을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1c5d-130">통화 파크에 대한 사용자 지정 보류 음악 파일은 비즈니스용 Skype 서버 재해 복구 프로세스의 일부로 백업되지 않습니다. 풀에 업로드된 파일이 손상되거나 삭제되면 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="d1c5d-131">통화 대기를 위해 업로드하는 사용자 지정 대기 음악 파일의 별도 백업 복사본을 항상 유지하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="d1c5d-p109">통화 대기 응용 프로그램은 Enterprise Voice의 구성 요소입니다. Enterprise Voice를 배포하면 통화 대기 응용 프로그램이 자동으로 설치되고 활성화됩니다. 그러나 통화 대기를 사용하려면 먼저 Enterprise Voice 관리자가 통화 대기를 구성하고 음성 정책을 통해 사용자가 사용할 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-p109">The Call Park application is a component of Enterprise Voice. When you deploy Enterprise Voice, the Call Park application is installed and activated automatically. Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="d1c5d-135">배포 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1c5d-135">Deployment and requirements</span></span>

<span data-ttu-id="d1c5d-136">통화 파크 응용 프로그램은 통화를 배포할 때 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="d1c5d-137">음성 정책을 구성하여 통화 파킹을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="d1c5d-138">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1c5d-138">Software requirements</span></span>

<span data-ttu-id="d1c5d-139">통화 파운데이션이 배포된 모든 프런트 엔드 서버 및 Standard Edition Server에는 Windows Server 2008 R2를 실행하는 서버에 대해 Windows Media 형식 런타임이 설치되어 있어야 합니다. 또는 Microsoft Media Foundation for servers for Windows Server 2012 또는 Windows Server 2012 R2를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="d1c5d-140">Windows Server 2008 R2의 경우 Windows Media 형식 런타임은 Windows 데스크톱 환경의 일부로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="d1c5d-141">통화 파운데이션이 재생하는 Windows Media 오디오(.wma) 파일에는 Windows Media 형식 런타임 또는 Microsoft Media Foundation이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="d1c5d-142">포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1c5d-142">Port requirements</span></span>

<span data-ttu-id="d1c5d-143">통화 파크 응용 프로그램은 SIP **수신 요청에 포트 5075를**  사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d1c5d-144">이 포트는 **Set-CsApplicationServer** cmdlet을 사용하여 변경할 수 있는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="d1c5d-145">이 cmdlet에 대한 자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="d1c5d-146">오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1c5d-146">Audio File requirements</span></span>

<span data-ttu-id="d1c5d-147">통화 파크 응용 프로그램은 보류된 음악에 대해 Windows Media 오디오(.wma) 파일만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="d1c5d-148">Microsoft Expression Encoder 4를 사용하여 대기 음악용으로 파일을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="d1c5d-149">식 인코더 4를 다운로드하려면 ["식 인코더 4"를 참조합니다.](https://go.microsoft.com/fwlink/p/?linkId=202843)</span><span class="sxs-lookup"><span data-stu-id="d1c5d-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="d1c5d-150">이 도구를 사용하여 파일을 .wma 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="d1c5d-151">통화 대기의 대기 음악 파일로 권장되는 형식은 Media 오디오 9, 44kHz, 16비트, 모노, CBR, 32kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1c5d-152">변환된 파일은 44kHz로 녹음되었더라도 전화에서는 16kHz로만 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="d1c5d-153">지원되는 클라이언트 및 통화</span><span class="sxs-lookup"><span data-stu-id="d1c5d-153">Supported clients and calls</span></span>

<span data-ttu-id="d1c5d-154">통화 파크에 대해 지원되는 클라이언트 및 통화 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="d1c5d-155">통화를 대기로 설정하는 데 지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d1c5d-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="d1c5d-156">모든 IP, PBX(Private Branch Exchange), PSTN(공중 전화망) 또는 휴대폰의 통화를 대기로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1c5d-p114">오디오 통화만 대기로 설정할 수 있습니다. 인스턴트 메시지 및 회의는 대기로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="d1c5d-159">다음 클라이언트는 통화 파크를 사용하여 통화를 파기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="d1c5d-160">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="d1c5d-160">Skype for Business</span></span>
    
- <span data-ttu-id="d1c5d-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d1c5d-161">Lync 2013</span></span>
    
- <span data-ttu-id="d1c5d-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d1c5d-162">Lync 2010</span></span>
    
- <span data-ttu-id="d1c5d-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="d1c5d-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="d1c5d-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="d1c5d-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="d1c5d-165">휴대폰에서는 통화 파크를 사용하여 통화를 파기할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="d1c5d-166">통화를 재개하는 데 지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d1c5d-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="d1c5d-p115">파킹된 통화 번호 범위는 가상 내선 번호(사용자나 전화가 할당되지 않은 내선 번호) 블록으로 구성됩니다. 파킹된 통화 번호를 가상 내선 번호로 구성하면 휴대폰 및 PSTN 전화에서 대기로 설정된 통화를 재개할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="d1c5d-169">페더레이션 사용자는 대기로 설정된 통화를 재개할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="d1c5d-170">다음 클라이언트는 통화 파크에 대한 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="d1c5d-171">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="d1c5d-171">Skype for Business</span></span>
    
- <span data-ttu-id="d1c5d-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d1c5d-172">Lync 2013</span></span>
    
- <span data-ttu-id="d1c5d-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d1c5d-173">Lync 2010</span></span>
    
- <span data-ttu-id="d1c5d-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="d1c5d-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="d1c5d-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="d1c5d-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="d1c5d-176">IP 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="d1c5d-176">IP common area phones</span></span>
    
- <span data-ttu-id="d1c5d-177">공통 영역 전화 및 PBX(Private Branch Exchange) 전화를 포함하여 비즈니스용 Skype 서버 인프라에 연결된 비 IP 전화</span><span class="sxs-lookup"><span data-stu-id="d1c5d-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="d1c5d-178">통화 파크 용량 계획</span><span class="sxs-lookup"><span data-stu-id="d1c5d-178">Call Park capacity planning</span></span>

<span data-ttu-id="d1c5d-179">다음 표에서는 용량 계획 요구 사항의 기준으로 사용할 수 있는 통화 파크 사용자 모델에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d1c5d-180">재해 복구 용량 계획을 위해 페어링된 풀의 각 풀은 두 풀 모두에서 통화 파크 서비스에 대한 작업을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c5d-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="d1c5d-181">**통화 대기 사용자 모델**</span><span class="sxs-lookup"><span data-stu-id="d1c5d-181">**Call Park User Model**</span></span>

|<span data-ttu-id="d1c5d-182">**메트릭**</span><span class="sxs-lookup"><span data-stu-id="d1c5d-182">**Metric**</span></span>|<span data-ttu-id="d1c5d-183">**프런트 엔드  <br/>  풀당(프런트 엔드 서버 8대)**</span><span class="sxs-lookup"><span data-stu-id="d1c5d-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="d1c5d-184">**Standard Edition Server별**</span><span class="sxs-lookup"><span data-stu-id="d1c5d-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d1c5d-185">대기 속도</span><span class="sxs-lookup"><span data-stu-id="d1c5d-185">Park rate</span></span>  <br/> |<span data-ttu-id="d1c5d-186">분당 8개</span><span class="sxs-lookup"><span data-stu-id="d1c5d-186">8 per minute</span></span>  <br/> |<span data-ttu-id="d1c5d-187">분당 1개</span><span class="sxs-lookup"><span data-stu-id="d1c5d-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="d1c5d-188">대기 중인 통화 재개 속도</span><span class="sxs-lookup"><span data-stu-id="d1c5d-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="d1c5d-189">분당 8개</span><span class="sxs-lookup"><span data-stu-id="d1c5d-189">8 per minute</span></span>  <br/> |<span data-ttu-id="d1c5d-190">분당 1개</span><span class="sxs-lookup"><span data-stu-id="d1c5d-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="d1c5d-191">평균 대기 시간</span><span class="sxs-lookup"><span data-stu-id="d1c5d-191">Average park duration</span></span>  <br/> |<span data-ttu-id="d1c5d-192">60초</span><span class="sxs-lookup"><span data-stu-id="d1c5d-192">60 seconds</span></span>  <br/> |<span data-ttu-id="d1c5d-193">60초</span><span class="sxs-lookup"><span data-stu-id="d1c5d-193">60 seconds</span></span>  <br/> |
   

