---
title: 팀 음성 Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 여러 국가의 기업에 대 한 팀 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786115"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="fa622-103">Contoso 사례 연구: 오디오 회의</span><span class="sxs-lookup"><span data-stu-id="fa622-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="fa622-104">오디오 회의에 대 한 이해를 얻으려면 &mdash; &mdash; [Office 365에서 오디오 회의](deploy-audio-conferencing-teams-landing-page.md)를 검토 한 다음, it의 비용, 사용 가능 여부, Contoso의 작동 방식에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="fa622-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="fa622-105">개요</span><span class="sxs-lookup"><span data-stu-id="fa622-105">Overview</span></span> 

<span data-ttu-id="fa622-106">오디오 회의의 경우 Contoso는 조직 내에서 잘 알려진 전화 번호와 외부를 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa622-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="fa622-107">Contoso는 이러한 번호를 가능 하면 유지 하기를 원했습니다 때문에, 음성 회의 브리지에 전용 및 공유 전화 번호를 지정 하는 방법에 대 한 정보를 검토 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa622-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="fa622-108">해당 조사에 따라 Contoso는 다음과 같이 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa622-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="fa622-109">오디오 회의 통화를 정기적으로 호스트 하는 모집단의 세그먼트만 오디오 회의 라이선스를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fa622-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="fa622-110">Contoso는 전용 전화 번호를 사용 하 고 오디오 회의에 사용 하기 위해 기존 번호를 이식 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa622-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="fa622-111">Contoso 사용자는 비즈니스용 Skype를 사용 하 고 있으며 모든 사용자의 사서함이 온라인 상태 이기 때문에 많은 사용자가 기존 모임이 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa622-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="fa622-112">Contoso는 [모임 마이그레이션 서비스 (MMS)를 사용 하 여](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) 최종 사용자가 팀 전용 모드로 변경 되는 경우 contoso에 대 한 기존 모임이 자동으로 업데이트 됨을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fa622-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="fa622-113">구성</span><span class="sxs-lookup"><span data-stu-id="fa622-113">Configuration</span></span>

<span data-ttu-id="fa622-114">오디오 회의와 관련 된 전화 번호를 전화 시스템 내에서 서비스 번호 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa622-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="fa622-115">전화 통신 회사의 기존 전화 번호를 Office 365으로 이식 하기 위해 통화 요금제를 사용 하는 위치의 경우, Contoso는 [서비스 전화 번호 가져오기](getting-service-phone-numbers.md)단계를 팔 로우 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa622-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="fa622-116">기술 시험 운용에서 최종 사용자에 게 오디오 회의 라이선스를 할당 하려면 Contoso 관리자가 [조직의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa622-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="fa622-117">비즈니스 파일럿 및 마이그레이션에 대해 Contoso는 [Azure Active Directory의 그룹 구성원 자격으로 사용자에 게 라이선스를 할당](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)하는 단계를 따라 그룹 기반 라이선스를 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa622-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 