---
title: Teams 음성 Contoso 사례 연구
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
description: 다국적 기업에 대한 Teams 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786115"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="6198d-103">Contoso 사례 연구: 오디오 회의</span><span class="sxs-lookup"><span data-stu-id="6198d-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="6198d-104">오디오 회의의 기능, 비용, 가용성 및 작동 방식에 대해 이해하기 위해 &mdash; &mdash; Contoso에서 [Office 365에서](deploy-audio-conferencing-teams-landing-page.md)오디오 회의를 검토했습니다.</span><span class="sxs-lookup"><span data-stu-id="6198d-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="6198d-105">개요</span><span class="sxs-lookup"><span data-stu-id="6198d-105">Overview</span></span> 

<span data-ttu-id="6198d-106">오디오 회의의 경우 Contoso는 외부뿐만 아니라 조직 내에서 잘 알려진 전화 번호를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="6198d-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="6198d-107">Contoso는 가능한 경우 이러한 번호를 유지 관리하기를 원하기 때문에 전용 및 공유 전화 번호를 오디오 회의 브리지에 할당하는 정보를 검토했습니다.</span><span class="sxs-lookup"><span data-stu-id="6198d-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="6198d-108">Contoso는 조사에 따라 다음과 같은 결정을 내렸다.</span><span class="sxs-lookup"><span data-stu-id="6198d-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="6198d-109">정기적으로 오디오 회의 통화를 호스트하는 인구의 세그먼트만 오디오 회의 라이선스를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6198d-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="6198d-110">Contoso는 전용 전화 번호를 사용하며 오디오 회의에 사용할 기존 번호를 포터링합니다.</span><span class="sxs-lookup"><span data-stu-id="6198d-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="6198d-111">Contoso 사용자가 비즈니스용 Skype를 사용 중이기 때문에 모든 사용자의 사서함이 온라인에 있기 때문에 많은 사용자가 기존 모임을 예약했습니다.</span><span class="sxs-lookup"><span data-stu-id="6198d-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="6198d-112">Contoso는 [MMS(모임](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) 마이그레이션 서비스)를 사용하여 최종 사용자를 TeamsOnly 모드로 변경하면 Contoso에 대해 기존 모임이 자동으로 업데이트되는 것을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="6198d-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="6198d-113">구성</span><span class="sxs-lookup"><span data-stu-id="6198d-113">Configuration</span></span>

<span data-ttu-id="6198d-114">오디오 회의와 연결된 전화 번호를 전화 시스템 내에서 서비스 번호라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6198d-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="6198d-115">통화 플랜을 사용하는 위치의 경우 기존 전화 번호를 통신사에서 Office 365로 포터링하기 위해 Contoso는 서비스 전화 번호로 이동하는 단계를 [따릅니다.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="6198d-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="6198d-116">Contoso 관리자는 기술 파일럿에서 오디오 회의 라이선스를 최종 사용자에게 할당하기 위해 조직의 오디오 회의 설정 관리 단계를 [따릅니다.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6198d-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="6198d-117">비즈니스 파일럿 및 마이그레이션을 위해 Contoso는 Azure Active Directory의 그룹 멤버 자격에 따라 사용자에게 라이선스 할당의 단계에 따라 그룹 기반 [라이선스를 사용했습니다.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="6198d-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 