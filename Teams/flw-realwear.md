---
title: RealWear 클라이언트용 Microsoft Teams에 대한 IT 관리자 정보(미리보기)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: A, ITAdmin은 RealWear 클라이언트용 Microsoft Teams에 대해 안내합니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67f595e6b037eb6091d3b4e03e3258a13e12a4d1
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909392"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="a751c-103">RealWear용 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a751c-103">Microsoft Teams for RealWear</span></span>

<span data-ttu-id="a751c-104">이 문서는 RealWear head wearables용 Microsoft Teams 클라이언트에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a751c-104">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="a751c-105">RealWear HMT-1 및 HMT-1Z1을 사용하는 최전방 작업자는 이제 팀에서 화상 통화를 사용하여 원격 전문가와 협력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a751c-105">Frontline Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="a751c-106">RealWear용 Teams는 음성으로 제어되는 사용자 인터페이스를 통해 현장 작업자가 100 % 핸즈프리 상태를 유지하면서 크고 위험한 환경에서 상황 인식을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="a751c-106">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="a751c-107">필드 직원은 실시간으로 해당 사용자에게 표시되는 내용을 표시하여 문제를 해결하는 시간을 단축하고 비싼 가동 중지 시간의 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a751c-107">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="a751c-108">RealWear용 Microsoft Teams를 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="a751c-108">How to deploy Microsoft Teams for RealWear</span></span>

- <span data-ttu-id="a751c-109">RealWear 장치를 릴리스 11.2이상으로 업데이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="a751c-109">RealWear devices updated to release 11.2 or above.</span></span> <span data-ttu-id="a751c-110">[여기](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/)에서 자세한 내용을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a751c-110">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>
- <span data-ttu-id="a751c-111">Realwear용 Microsoft Teams 클라이언트를 배포하는 데 필요한 [RealWear Foresight](https://cloud.realwear.com/)에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a751c-111">Access to [RealWear Foresight](https://cloud.realwear.com/) for distributing the Microsoft Teams client for Realwear.</span></span>

## <a name="required-licenses"></a><span data-ttu-id="a751c-112">필수 라이선스</span><span class="sxs-lookup"><span data-stu-id="a751c-112">Required Licenses</span></span>

<span data-ttu-id="a751c-113">Microsoft Teams 라이선스는 Microsoft 365 및 Office 365 구독의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="a751c-113">Microsoft Teams licenses are part of Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="a751c-114">RealWear용 Teams를 사용하는 데 별도의 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a751c-114">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="a751c-115">팀을 얻는 방법에 대한 자세한 내용은  [Microsoft Teams에 액세스하는 방법](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a751c-115">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="a751c-116">RealWear 장치 관리</span><span class="sxs-lookup"><span data-stu-id="a751c-116">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="a751c-117">Microsoft 엔드포인트 관리자</span><span class="sxs-lookup"><span data-stu-id="a751c-117">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="a751c-118">RealWear 장치는 Android 장치 관리자 모드를 사용하여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a751c-118">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="a751c-119">장치에 현재 Google 모바일 서비스(GMS)가 제공되지 않으므로 Android Enterprise를 통한 관리 지원이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a751c-119">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="a751c-120">Microsoft Endpoint Manager에서 RealWear 장치 관리에 대한 자세한 내용을 보려면 [Intune에서 Android 장치 관리자 등록](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a751c-120">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="a751c-121">정책에 대한 자세한 내용은 [Google 모바일 서비스가 없는 환경에서 Intune을 사용하는 방법](https://docs.microsoft.com/mem/intune/apps/manage-without-gms)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a751c-121">For more details on policies, see [How to use Intune in environments without Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="a751c-122">타사 EMM(Enterprise Mobility Manager)</span><span class="sxs-lookup"><span data-stu-id="a751c-122">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="a751c-123">타사 EMM에 대한 지침은 [지원되는 엔터프라이즈 이동성 관리 공급자](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a751c-123">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="a751c-124">최종 사용자 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="a751c-124">End-user content</span></span>

<span data-ttu-id="a751c-125">최종 사용자 관점에서 이에 대한 자세한 내용은 [RealWear용 Microsoft Teams 사용](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a751c-125">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>
