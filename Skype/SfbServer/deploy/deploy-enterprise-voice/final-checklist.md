---
title: 비즈니스용 Skype 서버에 대한 통화 제어 배포 최종 검사 목록
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
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 비즈니스용 Skype 서버 2013에서 CAC(통화 제어)를 배포하기 위한 최종 Enterprise Voice.
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830838"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="048bc-103">통화 제어 배포: 비즈니스용 Skype 서버의 최종 검사 목록</span><span class="sxs-lookup"><span data-stu-id="048bc-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="048bc-104">비즈니스용 Skype 서버 2013에서 CAC(통화 제어)를 배포하기 위한 최종 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="048bc-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="048bc-105">다음 검사 목록을 사용하여 CAC(통화 제어)를 배포하는 데 필요한 모든 구성 작업을 완료한지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="048bc-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="048bc-p101">하나 이상의 에지 서버가 배포된 경우 각 외부 인터페이스 IP 주소는 비트 마스크가 32인 네트워크 구성 설정의 서브넷 목록에 추가되어야 합니다. 또한 이 서브넷(IP 주소)을 A/V 에지 서비스가 배포된 지리적 위치의 네트워크 사이트 ID와 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="048bc-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="048bc-108">CAC를 구현하는 데 에지 서버가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="048bc-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="048bc-109">CAC가 사용하도록 설정되어 있는지 확인합니다.(비즈니스용 Skype 서버에서 통화 [입장](enable-call-admission-control.md)제어 사용에 지정된 경우).</span><span class="sxs-lookup"><span data-stu-id="048bc-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="048bc-110">CAC가 모든 중앙 사이트에서 사용하도록 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="048bc-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="048bc-111">이 수행은 토폴로지 작성기에서 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="048bc-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="048bc-112">게시할 때 경고가 생성되는 경우  *무시하지*  마십시오.</span><span class="sxs-lookup"><span data-stu-id="048bc-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="048bc-113">엔터프라이즈 네트워크에서 관리된 모든 서브넷이 네트워크 구성 설정에서 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="048bc-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="048bc-114">또한 비즈니스용 Skype의 네트워크 지역, 사이트 및 서브넷 배포에 설명된 모든 서브넷을 네트워크 사이트에 [연결해야 합니다.](deploy-network.md)</span><span class="sxs-lookup"><span data-stu-id="048bc-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="048bc-115">모든 프런트 엔드 서버, SBA(Survivable Branch Appliance), 오디오/비디오 회의 서버(별도의 풀에 있는 경우), 중재 서버의 서브넷이나 IP 주소가 네트워크 구성 설정에서 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="048bc-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

