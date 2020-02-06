---
title: 비즈니스용 Skype에서 알림 신청에 대 한 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 비즈니스용 Skype Server Enterprise Voice에서 알림 신청에 대 한 계획을 통해 조직에서 지정 하지 않은 전화 번호로 전화를 걸고 할 수 있는 작업을 구성 합니다. 오디오 파일 요구 사항이 포함 되어 있습니다.
ms.openlocfilehash: d160878030fad30dd3e91b78f54ffcdab722299f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803268"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a><span data-ttu-id="5c066-104">비즈니스용 Skype에서 알림 신청에 대 한 계획</span><span class="sxs-lookup"><span data-stu-id="5c066-104">Plan for the Announcement application in Skype for Business</span></span>

<span data-ttu-id="5c066-105">비즈니스용 Skype Server Enterprise Voice에서 알림 신청에 대 한 계획을 통해 조직에서 지정 하지 않은 전화 번호로 전화를 걸고 할 수 있는 작업을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-105">Planning for the announcement application in Skype for Business Server Enterprise Voice, which configures what to do with phone calls to unassigned phone numbers in your organizations.</span></span> <span data-ttu-id="5c066-106">오디오 파일 요구 사항이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-106">Includes audio file requirements.</span></span>

<span data-ttu-id="5c066-107">비즈니스용 Skype Server 알림 응용 프로그램을 사용 하면 전화 번호를 조직에 사용할 수 있지만 사용자 또는 휴대폰에 할당 되지 않은 수신 전화 통화 처리를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-107">The Skype for Business Server Announcement application enables you to configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or a phone.</span></span> <span data-ttu-id="5c066-108">이러한 통화를 미리 지정 된 대상 (전화 번호, SIP URI 또는 음성 메일)으로 전송 하거나 오디오 알림을 재생 하거나 모두 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-108">You can transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="5c066-109">알림 응용 프로그램을 사용 하면 발신자가 통화를 잘못 걸기 하 고 수신 중이거나 SIP 클라이언트에 오류 메시지가 표시 되는 상황을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-109">The Announcement application helps you avoid the situations in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="5c066-110">이 섹션에는 알림 응용 프로그램과 관련 된 계획 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-110">This section includes planning information that is specific to the Announcement application</span></span>

<span data-ttu-id="5c066-111">알림 응용 프로그램을 배포할 때 지정 되지 않은 번호를 다른 사용자가 전화를 걸 때 수행할 작업을 결정 하는 할당 되지 않은 번호 테이블을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-111">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="5c066-112">지정 하지 않은 번호 테이블에는 조직에 유효한 전화 번호 범위가 포함 되며 각 범위를 처리 하는 알림 응용 프로그램을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-112">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="5c066-113">발신자가 조직에 대해 유효한 전화 번호로 전화를 걸고 모든 사람에 게 배정 되지 않은 경우 비즈니스용 Skype 서버는 할당 되지 않은 번호 라우팅 테이블에서 해당 번호를 조회 하 고 해당 숫자가 속한 범위를 식별 하 여 해당 전화에 대 한 통화 경로를 해당 범위에 대해 지정 된 알림 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5c066-113">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Skype for Business Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="5c066-114">알림 응용 프로그램에서 통화에 응답 하 고 오디오 메시지를 재생 한 다음 (이렇게 구성한 경우), 통화 연결을 끊거나, 교환원 등의 미리 지정 된 대상에 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-114">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="5c066-115">비즈니스용 Skype Server Management Shell cmdlet을 사용 하 여 여러 음성 메시지를 구성 하거나 대상을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-115">You can use Skype for Business Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="5c066-116">할당되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-116">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="5c066-117">더 이상 사용 되지 않는 특정 번호를가지고 있고 각 숫자에 맞게 조정 된 메시지를 재생 하려는 경우에는 지정 되지 않은 번호 표에 해당 번호를 입력 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-117">If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table.</span></span> <span data-ttu-id="5c066-118">예를 들어 고객 서비스 데스크 번호를 변경한 경우 이전 고객 서비스 번호를 입력 하 고 새 번호를 제공 하는 공지 사항에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-118">For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number.</span></span> <span data-ttu-id="5c066-119">조직에서 나간 직원과 같이 배정 되지 않은 번호를 호출한 모든 사용자에 게 일반 메시지를 재생 하려는 경우 조직의 유효한 모든 확장에 대 한 범위를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-119">If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization.</span></span> <span data-ttu-id="5c066-120">할당 되지 않은 번호 테이블은 발신자가 현재 할당 되지 않은 번호로 전화를 걸 때마다 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-120">The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

## <a name="deployment-and-requirements"></a><span data-ttu-id="5c066-121">배포 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c066-121">Deployment and requirements</span></span>

<span data-ttu-id="5c066-122">등록 알림 응용 프로그램이 응답 그룹 응용 프로그램과 함께 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-122">Tthe Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="5c066-123">알림 및 응답 그룹 응용 프로그램은 엔터프라이즈 음성 배포의 표준 구성 요소입니다. 엔터프라이즈 음성을 배포 하는 경우 두 응용 프로그램이 모두 자동으로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-123">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="5c066-124">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c066-124">Software requirements</span></span>

<span data-ttu-id="5c066-125">알림 응용 프로그램을 실행 하는 모든 프런트 엔드 서버 또는 Standard Edition 서버에는 windows Server 2008 R2 또는 Windows Server 2012를 실행 하는 서버에 대해 Microsoft Media Foundation을 실행 하는 서버용 Windows Media 형식 런타임이 설치 되어 있어야 합니다. Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="5c066-125">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="5c066-126">Windows Server 2008 R2의 경우 windows Media 형식 런타임이 Windows 데스크톱 환경의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-126">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="5c066-127">알림 응용 프로그램이 공지 사항 및 음악에 대해 재생 하는 Windows media 오디오 (.wma) 파일에는 windows Media 형식 런타임 또는 Microsoft Media Foundation이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-127">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

### <a name="port-requirements"></a><span data-ttu-id="5c066-128">포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c066-128">Port Requirements</span></span>

<span data-ttu-id="5c066-129">알림 응용 프로그램에서는 SIP 수신 요청에 대해 **포트 5071** 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-129">The Announcement application uses **Port 5071** for SIP listening requests.</span></span>

> [!NOTE]
> <span data-ttu-id="5c066-130">이 포트는 기본 설정 이며, **Set-CsApplicationServer** cmdlet을 사용 하 여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-130">This port is the default setting, which you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="5c066-131">이 cmdlet에 대 한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c066-131">For details about this cmdlet, see the Skype for Business Server Management Shell documentation.</span></span>

### <a name="audio-file-requirements"></a><span data-ttu-id="5c066-132">오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c066-132">Audio File Requirements</span></span>

<span data-ttu-id="5c066-133">알림 응용 프로그램은 음악 및 알림에 대 한 웨이브 (.wav) 파일 형식과 Windows Media 오디오 (.wma) 파일 형식을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-133">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="5c066-134">알림 응용 프로그램에 대 한 오디오 파일 요구 사항은 응답 그룹 응용 프로그램의 경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c066-134">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="5c066-135">자세한 내용은 [응답 그룹에 대 한 기술 요구 사항을](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c066-135">For details, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>


