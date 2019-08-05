---
title: Microsoft 팀의 AppLocker 응용 프로그램 제어 정책
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: AppLocker 응용 프로그램 제어 정책으로 팀 데스크톱 클라이언트 응용 프로그램을 사용 하도록 설정 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "36182219"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="5fb8f-103">Microsoft 팀의 AppLocker 응용 프로그램 제어 정책</span><span class="sxs-lookup"><span data-stu-id="5fb8f-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="5fb8f-104">이 문서에서는 AppLocker 응용 프로그램 제어 정책으로 팀 데스크톱 클라이언트 앱을 사용 하도록 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="5fb8f-105">AppLocker 사용은 관리자가 아닌 사용자가 프로그램과 스크립트 실행을 제한 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="5fb8f-106">AppLocker에 대 한 자세한 내용 및 지침은 [applocker 란?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="5fb8f-107">AppLocker로 팀을 사용 하도록 설정 하는 프로세스에는 AppLocker 기반 whitelisting 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="5fb8f-108">정책은 그룹 정책 관리 소프트웨어 및/또는 AppLocker 용 Windows PowerShell cmdlet을 사용 하 여 생성 됩니다 (자세한 내용은 [applocker 기술 참조](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) 를 참조 하세요).</span><span class="sxs-lookup"><span data-stu-id="5fb8f-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="5fb8f-109">AppLocker 정책은 XML 형식으로 저장 되며 모든 텍스트 또는 XML 편집기를 사용 하 여 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="5fb8f-110">AppLocker로 whitelisting 팀</span><span class="sxs-lookup"><span data-stu-id="5fb8f-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="5fb8f-111">AppLocker 규칙은 규칙 모음으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="5fb8f-112">AppLocker 규칙은 대상 앱에 적용 되며 AppLocker 정책을 구성 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="5fb8f-113">팀을 허용 목록 모든 팀 앱 파일에 디지털 서명이 있으므로 [게시자 조건 규칙](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) 을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="5fb8f-114">팀 설치 디렉터리는 사용자에 게 쓸 수 있으므로 경로 규칙을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="5fb8f-115">또한 팀 클라이언트 앱이 업데이트 될 때마다 규칙이 업데이트 되어야 하므로 해시 규칙을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="5fb8f-116">팀 데스크톱 실행 파일은 디지털 서명 되므로 게시자 조건은 디지털 서명 및 포함 된 버전 특성에 따라 앱 파일을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="5fb8f-117">디지털 서명에는 앱 파일을 만든 회사에 대 한 정보가 포함 되어 있습니다 (게시자).</span><span class="sxs-lookup"><span data-stu-id="5fb8f-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="5fb8f-118">이진 리소스에서 가져온 버전 정보에는 해당 파일이 속한 제품의 이름과 응용 프로그램 파일의 버전 번호가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="5fb8f-119">Publisher 조건 규칙의 예</span><span class="sxs-lookup"><span data-stu-id="5fb8f-119">Example of publisher condition rules</span></span>

<span data-ttu-id="5fb8f-120">팀 클라이언트 앱 (모든 파일의 모든 버전)에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fb8f-120">For the Teams client app (all files, all versions):</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a><span data-ttu-id="5fb8f-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5fb8f-121">Related topics</span></span>
<span data-ttu-id="5fb8f-122">[AppLocker 란?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker 기술 참조](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="5fb8f-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>