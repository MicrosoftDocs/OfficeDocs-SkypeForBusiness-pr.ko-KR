---
title: 비즈니스용 Skype 서버에서 핵심 인프라에 대 한 모범 사례
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: 하드웨어 중복성 보장, 정전 으로부터 보호, 보안 업데이트 및 바이러스 백신 조치, 서버 활동 모니터링 등의 방법을 사용 하 여 시스템에서 내결함성 설계 단계를 이미 수행 했을 수 있습니다. 이러한 방법을 통해 비즈니스용 Skype 서버 인프라 뿐만 아니라 전체 네트워크에 대 한 혜택을 얻을 수 있습니다. 이러한 방법을 구현 하지 않은 경우 비즈니스용 Skype 서버를 배포 하기 전에이를 수행 하는 것이 좋습니다.
ms.openlocfilehash: c1f6a6ebe31276b8dbcd9037fa373baffc055fde
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196842"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="0ca2b-105">비즈니스용 Skype 서버에서 핵심 인프라에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="0ca2b-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="0ca2b-106">하드웨어 중복성 보장, 정전 으로부터 보호, 보안 업데이트 및 바이러스 백신 조치, 서버 활동 모니터링 등의 방법을 사용 하 여 시스템에서 내결함성 설계 단계를 이미 수행 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="0ca2b-107">이러한 방법을 통해 비즈니스용 Skype 서버 인프라 뿐만 아니라 전체 네트워크에 대 한 혜택을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="0ca2b-108">이러한 방법을 구현 하지 않은 경우 비즈니스용 Skype 서버를 배포 하기 전에이를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="0ca2b-109">비즈니스용 Skype 서버 배포의 서버가 가동 중지 시간이 발생할 수 있는 우발적 이거나 체계적 손상 으로부터 보호 하기 위해 다음과 같은 예방 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="0ca2b-110">보안 업데이트를 사용 하 여 서버를 최신 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="0ca2b-111">Microsoft 보안 알림 서비스에 가입 하면 Microsoft 제품에 대 한 보안 공지 릴리스 알림을 즉시 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="0ca2b-112">구독 하려면 [Microsoft 기술 보안 알림 웹 사이트로](https://go.microsoft.com/fwlink/p/?LinkId=145202)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="0ca2b-113">액세스 권한이 올바르게 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="0ca2b-114">무단 액세스를 방지 하는 물리적 환경에서 서버를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-114">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="0ca2b-115">모든 서버에 적절 한 바이러스 백신 소프트웨어가 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-115">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="0ca2b-116">최신 바이러스 서명 파일을 사용 하 여 소프트웨어를 최신 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-116">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="0ca2b-117">바이러스 백신 응용 프로그램의 자동 업데이트 기능을 사용 하 여 바이러스 서명을 최신 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-117">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="0ca2b-118">비즈니스용 Skype 서버를 설치 하는 컴퓨터에서는 필요 하지 않은 Windows Server 운영 체제 서비스를 사용 하지 않도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="0ca2b-119">서버를 일관 되 게 제어 하 고 완전 한 격리, 대체 또는 실패 한 디스크의 적절 하 고 안전 하 게 폐기 하지 않는 한, 전체 볼륨 암호화 시스템을 사용 하 여 데이터가 저장 되는 운영 체제와 디스크 드라이브를 암호화 합니다. 드라이브나.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="0ca2b-120">서버에 대 한 물리적 액세스를 매우 엄격 하 게 제어할 수 있는 경우가 아니면 서버의 모든 외부 직접 메모리 액세스 (DMA) 포트를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="0ca2b-121">비교적 쉽게 초기화할 수 있는 DMA 기반 공격으로, 개인 암호화 키와 같은 중요 한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca2b-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

