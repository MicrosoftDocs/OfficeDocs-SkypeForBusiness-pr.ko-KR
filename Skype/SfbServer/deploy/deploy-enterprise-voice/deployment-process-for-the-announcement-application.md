---
title: 비즈니스용 Skype 서버의 공지 응용 프로그램에 대한 배포 프로세스
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 비즈니스용 Skype 서버 2013의 배포 프로세스 및 Enterprise Voice.
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812308"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="55bab-103">비즈니스용 Skype 서버의 공지 응용 프로그램에 대한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="55bab-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="55bab-104">비즈니스용 Skype 서버 2013의 배포 프로세스 및 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="55bab-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="55bab-105">공지 Enterprise Voice 기능으로, 할당되지 않은 내선 번호(조직에 유효하지만 사람 또는 전화에 할당되지 않은 내선 번호)에 대한 통화를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bab-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="55bab-106">예를 들어 지정되지 않은 번호로의 통화에 대해 메시지를 재생하거나 다른 대상으로 전달하도록 구성하거나 이 두 가지를 모두 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bab-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="55bab-107">공지 사항을 배포할 때 공지 응용 프로그램은 프런트 엔드 서버 또는 Standard Edition 서버에 응답 그룹 응용 프로그램의 기능으로 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="55bab-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="55bab-108">오디오 파일을 업로드하거나 TTS(텍스트 음성 변환)를 구성하고 지정되지 않은 번호 테이블을 구성하여 알림을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bab-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="55bab-109">이 섹션에서는 공지 사항 응용 프로그램 배포와 관련된 단계에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="55bab-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="55bab-110">공지 사항을 구성하기 Enterprise Voice 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bab-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="55bab-111">공지사항 응용 프로그램에 필요한 구성 요소는 배포할 때 설치 및 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="55bab-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="55bab-112">**알림 배포 프로세스**</span><span class="sxs-lookup"><span data-stu-id="55bab-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="55bab-113">**작업 단계**</span><span class="sxs-lookup"><span data-stu-id="55bab-113">**Phase**</span></span>|<span data-ttu-id="55bab-114">**단계**</span><span class="sxs-lookup"><span data-stu-id="55bab-114">**Steps**</span></span>|<span data-ttu-id="55bab-115">**역할**</span><span class="sxs-lookup"><span data-stu-id="55bab-115">**Roles**</span></span>|<span data-ttu-id="55bab-116">**배포 설명서**</span><span class="sxs-lookup"><span data-stu-id="55bab-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55bab-117">알림 설정 구성</span><span class="sxs-lookup"><span data-stu-id="55bab-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="55bab-118">오디오 파일을 녹음하여 업로드하거나 TTS(텍스트 음성 변환)를 사용하여 알림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55bab-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="55bab-119">지정되지 않은 번호 표의 지정되지 않은 번호 범위를 구성하여 적절한 알림과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="55bab-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="55bab-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="55bab-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="55bab-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="55bab-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="55bab-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="55bab-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="55bab-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="55bab-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="55bab-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="55bab-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="55bab-125">비즈니스용 Skype 서버에서 공지 만들기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="55bab-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="55bab-126">비즈니스용 Skype 서버에서 미지정 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="55bab-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="55bab-127">알림 배포 확인</span><span class="sxs-lookup"><span data-stu-id="55bab-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="55bab-128">알림 듣기를 테스트하여 구성이 제대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="55bab-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="55bab-129">(선택 사항) 비즈니스용 Skype에서 공지사항 배포 확인</span><span class="sxs-lookup"><span data-stu-id="55bab-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

