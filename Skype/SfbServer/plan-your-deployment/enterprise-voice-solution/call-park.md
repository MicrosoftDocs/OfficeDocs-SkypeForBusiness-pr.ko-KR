---
title: 비즈니스용 Skype에서 통화 공원에 대 한 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 비즈니스용 Skype Server Enterprise Voice의 통화 공원에 대 한 계획을 통해 통화를 대기 상태로 전환 하 고 전화를 부서로 전송할 수 있습니다. 용량 계획, 지원 되는 통화 및 지원 되는 클라이언트를 포함 합니다.
ms.openlocfilehash: 3272efe89ac995b304d96ad7ce5660144641073b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187770"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="79dfb-104">비즈니스용 Skype에서 통화 공원에 대 한 계획</span><span class="sxs-lookup"><span data-stu-id="79dfb-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="79dfb-105">비즈니스용 Skype Server Enterprise Voice의 통화 공원에 대 한 계획을 통해 통화를 대기 상태로 전환 하 고 전화를 부서로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="79dfb-106">용량 계획, 지원 되는 통화 및 지원 되는 클라이언트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="79dfb-107">통화 공원 응용 프로그램을 통해 엔터프라이즈 음성 사용자는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="79dfb-108">통화를 대기 상태로 설정한 다음 같은 휴대폰 또는 다른 전화기에서 통화를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="79dfb-109">통화를 대기 또는 일반 영역 (예: 영업부 또는 공통 지역 전화국에 거주 하는 영업 부서나 웨어하우스로)으로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="79dfb-110">통화를 대기 상태로 전환 하 고 다른 통화를 위해 원래 응답 전화를 무료로 유지 하세요.</span><span class="sxs-lookup"><span data-stu-id="79dfb-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="79dfb-111">사용자가 통화를 전환 하면 비즈니스용 Skype Server는 전화를 검색할 때까지 통화가 대기 하는 궤도 라고 하는 임시 번호로 통화를 전송 합니다. 비즈니스용 Skype 서버는 통화를 파킹 한 사용자에 게 궤도를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="79dfb-112">파킹 된 통화를 검색 하기 위해 사용자는 궤도 번호로 전화를 걸거나 대화 창에서 궤도 링크 또는 단추를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="79dfb-113">통화를 파킹 한 사용자는 다른 사용자에 게 궤도 번호를 전달 하는 메신저 대화 (인스턴트 메시징) 또는 페이징 시스템 등의 외부 메커니즘을 사용 하 여 전화를 받도록 다른 사람에 게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-113">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="79dfb-114">통화를 파킹 한 사용자는 통화가 검색 될 때 알림을 받도록 대화 창을 열어 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-114">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="79dfb-115">궤도 범위는 전역적으로 고유 하므로, 라우팅이 적절 하 게 구성 된 경우 비즈니스용 Skype 서버 사이트 또는 PBX 전화기에서 전화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="79dfb-116">구성 가능한 시간 내에 호출이 검색 되지 않는 경우에는 통화가 대기 하는 사용자에 게 다시 전화가 울립니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="79dfb-117">해당 사용자가 ringback에 응답 하지 않는 경우 통화는 교환원 (예: 구성 된 경우)과 같은 대체 대상으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="79dfb-118">통화가 1 ~ 10 번 전송 되기 전에 다시 울릴 횟수를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="79dfb-119">통화에 대 한 답이 없는 경우 통화의 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="79dfb-120">통화가 검색 되거나 연결이 끊어지면 궤도가 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="79dfb-121">통화 공원를 배포 하는 경우 파킹 통화에 대 한 내선 번호 범위를 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="79dfb-122">이러한 확장은 사용자 또는 휴대폰을 할당 하지 않은 가상 확장 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="79dfb-123">그런 다음 내선 번호 범위를 사용 하 여 통화 공원 표를 구성 하 고 각 범위를 처리 하는 통화 공원 응용 프로그램을 호스팅하는 응용 프로그램 서비스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="79dfb-124">각 프런트 엔드 풀에는 풀에서 파킹 된 통화를 관리 하는 데 사용 되는 해당 백 엔드 서버에 대 한 통화 공원 테이블이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="79dfb-125">궤도 범위 목록은 중앙 관리 저장소에 저장 되며 대상 풀로 orbits를 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="79dfb-126">통화 공원 응용 프로그램을 배포 하 고 구성 하는 각 비즈니스용 Skype 서버 풀에는 하나 이상의 궤도 범위가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="79dfb-127">궤도 범위는 비즈니스용 Skype 서버 배포에서 전역적으로 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="79dfb-128">또한 시간이 초과 되는 경우 통화가 리디렉션되는 위치, 휴대 중에는 전화의 상대방이 음악을 듣게 되는지 등 다른 통화 대기 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-128">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="79dfb-129">통화 대기 중에 음악 파일을 재생 하도록 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-129">You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79dfb-130">통화 공원에 대 한 사용자 지정 음악 보관 파일은 비즈니스용 Skype 서버 재해 복구 프로세스의 일부로 백업 되지 않으며 풀에 업로드 된 파일이 손상, 손상 또는 지워진 경우 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="79dfb-131">통화 공원에 대해 업로드 한 사용자 지정 음악 보관 파일의 별도의 백업 복사본을 항상 보관 하세요.</span><span class="sxs-lookup"><span data-stu-id="79dfb-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="79dfb-132">통화 공원 응용 프로그램은 엔터프라이즈 음성의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="79dfb-133">엔터프라이즈 음성을 배포 하는 경우 통화 공원 응용 프로그램이 자동으로 설치 되 고 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="79dfb-134">통화 대기를 사용 하기 전에 엔터프라이즈 음성 관리자가 음성 정책을 통해 사용자에 게이를 구성 하 고 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="79dfb-135">배포 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="79dfb-135">Deployment and requirements</span></span>

<span data-ttu-id="79dfb-136">전화 공원 응용 프로그램은 엔터프라이즈 음성을 배포할 때 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="79dfb-137">음성 정책을 구성 하 여 통화 파킹 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="79dfb-138">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="79dfb-138">Software requirements</span></span>

<span data-ttu-id="79dfb-139">통화 공원를 배포 하는 모든 프런트 엔드 서버 및 Standard Edition 서버는 windows Server 2008 R2 또는 windows server 2012 또는 Windows Server를 실행 하는 서버에 대 한 Microsoft Media Foundation을 실행 하는 서버용 Windows Media 형식 런타임을 설치 해야 합니다. 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="79dfb-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="79dfb-140">Windows Server 2008 R2의 경우 windows Media 형식 런타임이 Windows 데스크톱 환경의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="79dfb-141">Windows Media 오디오 (.wma) 파일에는 음악을 저장할 때 재생 되는 파킹에 대 한 기본 설정 또는 Microsoft Media Foundation이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="79dfb-142">포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="79dfb-142">Port requirements</span></span>

<span data-ttu-id="79dfb-143">통화 공원 응용 프로그램은 SIP 수신 요청에 대해 **포트 5075** 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="79dfb-144">이 포트는 **Set CsApplicationServer** cmdlet을 사용 하 여 변경할 수 있는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="79dfb-145">이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79dfb-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="79dfb-146">오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="79dfb-146">Audio File requirements</span></span>

<span data-ttu-id="79dfb-147">통화 공원 응용 프로그램은 음악을 저장할 때 Windows Media 오디오 (.wma) 파일만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="79dfb-148">Microsoft Expression Encoder 4를 사용 하 여 음악을 저장할 때 파일을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="79dfb-149">식 인코더 4를 다운로드 하려면 ["식 인코더 4"](https://go.microsoft.com/fwlink/p/?linkId=202843)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79dfb-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="79dfb-150">이 도구를 사용 하 여 파일을 .wma 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="79dfb-151">통화 대기 파일에 권장 되는 형식은 미디어 오디오 9, 44 kHz, 16 비트, 모노, CBR, 32 kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79dfb-152">44 kHz에 녹음 한 경우에도 변환 된 파일은 휴대폰을 통해 16 kHz 에서만 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="79dfb-153">지원 되는 클라이언트 및 통화</span><span class="sxs-lookup"><span data-stu-id="79dfb-153">Supported clients and calls</span></span>

<span data-ttu-id="79dfb-154">통화 공원에 대해 지원 되는 클라이언트 및 통화 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="79dfb-155">파킹 통화에 지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="79dfb-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="79dfb-156">모든 IP, PBX (사설 브랜치 교환), PSTN (공개 전환 전화 네트워크) 또는 휴대 전화는 파킹 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79dfb-157">오디오 통화만 파킹 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-157">Only audio calls can be parked.</span></span> <span data-ttu-id="79dfb-158">인스턴트 메시지와 회의는 파킹 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-158">Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="79dfb-159">다음 클라이언트는 통화 공원를 사용 하 여 통화를 대기 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="79dfb-160">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="79dfb-160">Skype for Business</span></span>
    
- <span data-ttu-id="79dfb-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="79dfb-161">Lync 2013</span></span>
    
- <span data-ttu-id="79dfb-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="79dfb-162">Lync 2010</span></span>
    
- <span data-ttu-id="79dfb-163">Lync 2010 수행자</span><span class="sxs-lookup"><span data-stu-id="79dfb-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="79dfb-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="79dfb-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="79dfb-165">휴대 전화는 통화 대기를 사용 하 여 통화를 대기 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="79dfb-166">통화 검색에 지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="79dfb-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="79dfb-167">궤도 범위는 가상 확장 블록 (할당 된 사용자 또는 전화기 없이 확장)으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-167">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone).</span></span> <span data-ttu-id="79dfb-168">Orbits를 가상 확장으로 구성 하는 경우 휴대 전화 및 PSTN 전화는 파킹 된 전화를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-168">When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="79dfb-169">페더레이션 사용자는 파킹 된 전화를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="79dfb-170">다음 클라이언트는 통화 공원에서 파킹 된 통화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="79dfb-171">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="79dfb-171">Skype for Business</span></span>
    
- <span data-ttu-id="79dfb-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="79dfb-172">Lync 2013</span></span>
    
- <span data-ttu-id="79dfb-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="79dfb-173">Lync 2010</span></span>
    
- <span data-ttu-id="79dfb-174">Lync 2010 수행자</span><span class="sxs-lookup"><span data-stu-id="79dfb-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="79dfb-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="79dfb-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="79dfb-176">IP 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="79dfb-176">IP common area phones</span></span>
    
- <span data-ttu-id="79dfb-177">일반 지역 전화 및 PBX (사설 지사 교환) 전화를 포함 하 여 비즈니스용 Skype 서버 인프라에 연결 된 비 IP 전화</span><span class="sxs-lookup"><span data-stu-id="79dfb-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="79dfb-178">통화 공원 용량 계획</span><span class="sxs-lookup"><span data-stu-id="79dfb-178">Call Park capacity planning</span></span>

<span data-ttu-id="79dfb-179">다음 표에서는 용량 계획 요구 사항의 기준으로 사용할 수 있는 통화 공원 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="79dfb-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="79dfb-180">재해 복구 용량 계획을 위해 쌍으로 연결 된 풀의 각 풀은 두 풀의 통화 파킹 서비스에 대 한 작업 부하를 처리할 수 있어야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="79dfb-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="79dfb-181">**통화 공원 사용자 모델**</span><span class="sxs-lookup"><span data-stu-id="79dfb-181">**Call Park User Model**</span></span>

|<span data-ttu-id="79dfb-182">**미터**</span><span class="sxs-lookup"><span data-stu-id="79dfb-182">**Metric**</span></span>|<span data-ttu-id="79dfb-183">**프런트 엔드 풀 <br/> 단위 (프런트 엔드 서버 8 개)**</span><span class="sxs-lookup"><span data-stu-id="79dfb-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="79dfb-184">**스탠더드 에디션 서버 당**</span><span class="sxs-lookup"><span data-stu-id="79dfb-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="79dfb-185">공원 요금</span><span class="sxs-lookup"><span data-stu-id="79dfb-185">Park rate</span></span>  <br/> |<span data-ttu-id="79dfb-186">분당 8</span><span class="sxs-lookup"><span data-stu-id="79dfb-186">8 per minute</span></span>  <br/> |<span data-ttu-id="79dfb-187">분당 1</span><span class="sxs-lookup"><span data-stu-id="79dfb-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="79dfb-188">파킹 통화 속도 검색</span><span class="sxs-lookup"><span data-stu-id="79dfb-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="79dfb-189">분당 8</span><span class="sxs-lookup"><span data-stu-id="79dfb-189">8 per minute</span></span>  <br/> |<span data-ttu-id="79dfb-190">분당 1</span><span class="sxs-lookup"><span data-stu-id="79dfb-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="79dfb-191">평균 공원 기간</span><span class="sxs-lookup"><span data-stu-id="79dfb-191">Average park duration</span></span>  <br/> |<span data-ttu-id="79dfb-192">60 초</span><span class="sxs-lookup"><span data-stu-id="79dfb-192">60 seconds</span></span>  <br/> |<span data-ttu-id="79dfb-193">60 초</span><span class="sxs-lookup"><span data-stu-id="79dfb-193">60 seconds</span></span>  <br/> |
   

