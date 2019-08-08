---
title: 통화 허용 제어 배포 최종 비즈니스용 Skype Server의 검사 목록
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
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 비즈니스용 Skype Server Enterprise Voice에서 호출 허용 제어 (CAC) 배포에 대 한 최종 검사 목록입니다.
ms.openlocfilehash: 275afdfcb3c5e2b7cc635e073bcb5b9ba5edc853
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240570"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="37a6b-103">통화 허용 제어 배포: 비즈니스용 Skype 서버에 대 한 최종 검사 목록</span><span class="sxs-lookup"><span data-stu-id="37a6b-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="37a6b-104">비즈니스용 Skype Server Enterprise Voice에서 호출 허용 제어 (CAC) 배포에 대 한 최종 검사 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="37a6b-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="37a6b-105">다음 검사 목록을 사용 하 여 CAC (Call 허용 제어)를 배포 하는 데 필요한 모든 구성 작업을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6b-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="37a6b-106">하나 이상의 Edge 서버가 배포 된 경우 각 외부 인터페이스 IP 주소를 네트워크 구성 설정의 서브넷 목록에 추가 해야 하며 비트 마스크는 32입니다.</span><span class="sxs-lookup"><span data-stu-id="37a6b-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="37a6b-107">또한이 서브넷 (IP 주소)을 A/V Edge 서비스가 배포 된 지리적 위치에 대 한 네트워크 사이트 ID와 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6b-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="37a6b-108">Edge 서버는 CAC를 구현 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a6b-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="37a6b-109">[비즈니스용 Skype 서버의 통화 허용 제어 사용](enable-call-admission-control.md)에 지정 된 대로 CAC가 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6b-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="37a6b-110">모든 중앙 사이트에서 CAC가 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6b-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="37a6b-111">토폴로지 작성기를 통해이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a6b-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="37a6b-112">게시할 때 경고가 생성 되 면이를 무시 *하지 마세요* .</span><span class="sxs-lookup"><span data-stu-id="37a6b-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="37a6b-113">엔터프라이즈 네트워크에서 관리 되는 모든 서브넷이 네트워크 구성 설정에서 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6b-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="37a6b-114">또한 [비즈니스용 Skype의 네트워크 지역, 사이트 및 서브넷 배포](deploy-network.md)에 설명 된 대로 모든 서브넷을 네트워크 사이트에 연결 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6b-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="37a6b-115">모든 프런트 엔드 서버의 서브넷 또는 IP 주소, Survivable Branch 기기 (SBAs), 오디오/비디오 회의 서버 (별도의 풀에 있는 경우) 및 중재 서버가 네트워크 구성 설정에 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a6b-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

