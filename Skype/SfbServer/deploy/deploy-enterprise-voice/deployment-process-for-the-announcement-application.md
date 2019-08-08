---
title: 비즈니스용 Skype 서버의 알림 신청에 대 한 배포 프로세스
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
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 비즈니스용 Skype Server Enterprise Voice의 알림 신청에 대 한 배포 프로세스 및 단계.
ms.openlocfilehash: 2edb9364408658e9a164210a9fcd5a0196b10da7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245767"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="281b2-103">비즈니스용 Skype 서버의 알림 신청에 대 한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="281b2-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="281b2-104">비즈니스용 Skype Server Enterprise Voice의 알림 신청에 대 한 배포 프로세스 및 단계.</span><span class="sxs-lookup"><span data-stu-id="281b2-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="281b2-105">알림 신청은 할당 되지 않은 확장명 (조직에 대해 유효 하지만 사용자 또는 휴대폰에 할당 되지 않은 확장명)에 대 한 호출을 구성할 수 있는 Enterprise Voice 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="281b2-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="281b2-106">예를 들어 지정 하지 않은 번호로 통화를 구성 하 여 메시지를 재생 하거나 다른 대상 또는 둘 다로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="281b2-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="281b2-107">알림 응용 프로그램은 엔터프라이즈 음성을 배포할 때 프런트 엔드 서버 또는 Standard Edition 서버에 응답 그룹 응용 프로그램의 기능으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="281b2-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="281b2-108">오디오 파일을 업로드 하거나 텍스트 읽어주기 (TTS)를 구성 하 고 할당 되지 않은 번호 표를 구성 하 여 알림을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="281b2-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="281b2-109">이 섹션에서는 알림 신청 배포 단계에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="281b2-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="281b2-110">알림을 구성 하기 전에 엔터프라이즈 음성을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="281b2-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="281b2-111">엔터프라이즈 음성을 구축할 때 알림 응용 프로그램에 필요한 구성 요소를 설치 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="281b2-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="281b2-112">**알림 배포 프로세스**</span><span class="sxs-lookup"><span data-stu-id="281b2-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="281b2-113">**단계의**</span><span class="sxs-lookup"><span data-stu-id="281b2-113">**Phase**</span></span>|<span data-ttu-id="281b2-114">**방법은**</span><span class="sxs-lookup"><span data-stu-id="281b2-114">**Steps**</span></span>|<span data-ttu-id="281b2-115">**역할**</span><span class="sxs-lookup"><span data-stu-id="281b2-115">**Roles**</span></span>|<span data-ttu-id="281b2-116">**배포 설명서**</span><span class="sxs-lookup"><span data-stu-id="281b2-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="281b2-117">알림 설정 구성</span><span class="sxs-lookup"><span data-stu-id="281b2-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="281b2-118">오디오 파일을 기록 및 업로드 하거나 텍스트 음성 변환 (TTS)을 사용 하 여 알림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="281b2-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="281b2-119">지정 하지 않은 번호 표에서 할당 되지 않은 번호 범위를 구성 하 고 적절 한 공지와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="281b2-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="281b2-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="281b2-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="281b2-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="281b2-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="281b2-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="281b2-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="281b2-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="281b2-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="281b2-124">Csviewadministrator</span><span class="sxs-lookup"><span data-stu-id="281b2-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="281b2-125">비즈니스용 Skype 서버에서 공지 사항 만들기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="281b2-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="281b2-126">비즈니스용 Skype 서버에서 할당 되지 않은 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="281b2-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="281b2-127">공지 사항 배포 확인</span><span class="sxs-lookup"><span data-stu-id="281b2-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="281b2-128">알림을 청취 하 여 테스트를 수행 하 여 구성이 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="281b2-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="281b2-129">) 비즈니스용 Skype에서 알림 배포 확인</span><span class="sxs-lookup"><span data-stu-id="281b2-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

