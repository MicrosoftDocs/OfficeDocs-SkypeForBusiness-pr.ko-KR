---
title: AppLocker 제어 정책
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: AppLocker 애플리케이션 제어 정책을 사용하여 Teams 데스크톱 클라이언트 애플리케이션을 사용하도록 설정하는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e70fc4502851137494c316db9eff7faefc140d1
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526694"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="02b17-103">Microsoft Teams의 AppLocker 애플리케이션 제어 정책</span><span class="sxs-lookup"><span data-stu-id="02b17-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="02b17-104">이 문서에서는 AppLocker 애플리케이션 제어 정책을 사용하여 Teams 데스크톱 클라이언트 앱을 사용하도록 설정하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="02b17-105">AppLocker의 사용은 비관리자에 의해 프로그램 및 스크립트 실행을 제한하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="02b17-106">AppLocker에 대한 자세한 내용은 [AppLocker란?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)</span><span class="sxs-lookup"><span data-stu-id="02b17-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="02b17-107">AppLocker에서 Teams를 사용하도록 설정하는 프로세스에는 AppLocker 기반 허용 목록 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="02b17-108">정책은 그룹 정책 관리 소프트웨어 및/또는 AppLocker용 Windows PowerShell cmdlet을 사용하여 만들어집니다(자세한 내용은 [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) 기술 참조).</span><span class="sxs-lookup"><span data-stu-id="02b17-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="02b17-109">AppLocker 정책은 XML 형식으로 저장되고 모든 텍스트 또는 XML 편집기로 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="02b17-110">AppLocker를 사용하여 Teams 허용 목록</span><span class="sxs-lookup"><span data-stu-id="02b17-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="02b17-111">AppLocker 규칙은 규칙 컬렉션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="02b17-112">AppLocker 규칙은 대상 앱에 적용하며 AppLocker 정책을 구성하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="02b17-113">Teams를 허용하려면 모든 Teams [](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) 앱 파일이 디지털 서명되어 게시자 조건 규칙을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-113">To allow Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="02b17-114">Teams 설치 디렉터리는 사용자가 사용할 수 있기 때문에 경로 규칙을 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="02b17-115">또한 Teams 클라이언트 앱이 업데이트될 때마다 규칙을 업데이트해야 하기 때문에 해시 규칙을 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="02b17-116">Teams 데스크톱 실행 파일은 디지털 서명이 됐기 때문에 게시자 조건은 디지털 서명 및 포함된 버전 특성을 기반으로 앱 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="02b17-117">디지털 서명에는 앱 파일(게시자)을 만든 회사에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="02b17-118">이진 리소스에서 얻은 버전 정보에는 파일이 포함된 제품의 이름과 애플리케이션 파일의 버전 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="02b17-119">게시자 조건 규칙 예제</span><span class="sxs-lookup"><span data-stu-id="02b17-119">Example of publisher condition rules</span></span>

<span data-ttu-id="02b17-120">Teams 클라이언트 앱(모든 파일, 모든 버전)의 경우 DLL 규칙에 따라 실행 가능한 & 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02b17-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="02b17-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="02b17-121">Related topics</span></span>
<span data-ttu-id="02b17-122">[AppLocker란?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker 기술 참조](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="02b17-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>
