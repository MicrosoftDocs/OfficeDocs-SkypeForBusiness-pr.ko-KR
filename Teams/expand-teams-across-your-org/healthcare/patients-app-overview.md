---
title: '팀 용 환자 앱 관리자 '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: 팀 용 환자 앱 관리자
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749560"
---
# <a name="patients-app-overview"></a><span data-ttu-id="7021e-103">환자 앱 개요</span><span class="sxs-lookup"><span data-stu-id="7021e-103">Patients app overview</span></span>

<span data-ttu-id="7021e-104">환자 응용 프로그램은 모든 팀 사용자가 사용할 수 있는 Microsoft 팀 스토어 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-104">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="7021e-105">앱은 임상 팀 (예: Nurses, 의사, 사교 작업자)으로 구성 되는 환자 팀에서 환자 목록을 반올림 및 검토 하 여 라운드 및 interdisciplinary 팀 모임에서 일반 환자 모니터링에 이르기까지 다양 한 시나리오를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-105">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>   

<span data-ttu-id="7021e-106">앱에는 두 가지 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-106">The app has two modes:</span></span> 

- <span data-ttu-id="7021e-107">Emr를 통해 FA r을 통해 연결 하는 EMR 연결 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-107">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="7021e-108">EMR 연결 모드 앱은 비공개 미리 보기에서 유지 되며, 관련 고객 또는 관리자가 Office 365 테 넌 트에 대 한 정보로 teamsforhealthcare@service.microsoft.com에서 Microsoft 전자 메일을 삭제 하 여 앱에 대 한 액세스를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-108">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at teamsforhealthcare@service.microsoft.com with information about their Office 365 tenant.</span></span> 
- <span data-ttu-id="7021e-109">주의 팀이 환자 정보를 수동으로 추가/지참물 할 수 있도록 해 주는 수동 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-109">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="7021e-110">최종 사용자가 기본적으로 다운로드할 수 있도록 응용 프로그램을 팀 앱 저장소에서 사용할 수 있으며, 공개 미리 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-110">The application is available in the Teams app store for end users to download by default and is in public preview.</span></span> <span data-ttu-id="7021e-111">[Microsoft 팀에서 앱 설치 정책을](../../teams-app-setup-policies.md) 사용 하 여 특정 사용자 섹션으로 앱을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-111">The app can be restricted to certain sections of users using [app setup policies in Microsoft Teams](../../teams-app-setup-policies.md)</span></span>



## <a name="usage-example"></a><span data-ttu-id="7021e-112">사용 예제</span><span class="sxs-lookup"><span data-stu-id="7021e-112">Usage example</span></span>

<span data-ttu-id="7021e-113">의료 wards의 모든 교대 근무에 대 한 세션을 반올림 하는 동안 nursing 스테이션에서 clinicians를 수집 하 여 진행 중인 환자에 대 한 최신 업데이트를 논의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-113">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="7021e-114">중요 한 주요 메트릭 (반드시 의료이 아닌 환자의 의료 기록)을 강조 표시 하 고 해당 진단을 기반으로 방전 시킬 수 있는 적절 한 glide 경로에 환자를 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-114">They highlight the key critical metrics (not necessarily medical or that its explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="7021e-115">이러한 환자를 반올림 하기 위해, 무료 nurse는 모든 clinicians이 추가 된 팀에 환자 앱을 설정 하 고 환자 목록에 환자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-115">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="7021e-116">라운드를 진행 하는 동안 환자에 대 한 nurses 및 기타 주의 givers는 모바일 장치에서 Microsoft 팀과 환자 앱에 액세스 하 고, 해당 장치에서 관련 환자 정보를 업데이트 하 고, 의료 팀의 다른 사용자가 해당 업데이트 및 메모를 볼 수 있습니다. 동기화 상태를 유지 합니다. 교대 근무의 시작 및 끝 부분에는 여러 displicinary 팀 모임이 있어 환자 목록을 통해 환자 앱을 사용 하 고, 큰 디스플레이 화면에서 환자 앱을 사용 하 여 각 환자에 대 한 정보를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-116">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-displicinary team meetings to go over the patient list and use the Patients App to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="7021e-117">일부 경우에 따라 일부 clinicians는 이러한 팀 모임에 원격으로 전화를 걸 수 있으며 여전히 토론에 포함 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-117">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span> 

## <a name="configure-patients-app"></a><span data-ttu-id="7021e-118">환자 앱 구성</span><span class="sxs-lookup"><span data-stu-id="7021e-118">Configure Patients app</span></span>

<span data-ttu-id="7021e-119">EMR 모드 환자 앱을 사용 하기 위해 환경을 준비 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에 전자 의료 기록 통합](patients-app.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7021e-119">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="7021e-120">또한 조직에 대해 환자 앱을 사용 하도록 설정 하려면 [Microsoft 팀에서 앱 설정 관리 정책도](../../teams-app-setup-policies.md) 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7021e-120">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a><span data-ttu-id="7021e-121">관련 주제</span><span class="sxs-lookup"><span data-stu-id="7021e-121">Related topics</span></span>

[<span data-ttu-id="7021e-122">Microsoft Teams에 전자 의료 레코드 통합</span><span class="sxs-lookup"><span data-stu-id="7021e-122">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
