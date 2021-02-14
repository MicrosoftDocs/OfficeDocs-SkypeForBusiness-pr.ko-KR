---
title: Lync Server 2010용 에지 서버 FQDN 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 외부 설정에서 속성을 정의하려면 다음을 구성합니다.
ms.openlocfilehash: 6075fab9dbc820b725beec8be4a674a828b4c7d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807098"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="cd5a3-103">Lync Server 2010용 에지 서버 FQDN 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="cd5a3-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="cd5a3-104">외부 설정에서 속성을 **정의하려면** 다음을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a3-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="cd5a3-105">웹 회의 및 오디오/비디오에 대해 고유한 풀 FQDN 및 IP 주소를 정의하려면 웹 회의 및 A/V에 대해 별도의 **FQDN** 및 IP 주소 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a3-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd5a3-106">별도의 FQDN 및 IP 주소에 대한 확인란을 선택하지 않는 경우 에지 서버에서 제공하는 세 가지 서비스 각각에 대해 고유한 포트를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a3-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="cd5a3-107">구성할 유일한 FQDN은 액세스 에지 서비스에 연결된 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a3-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="cd5a3-108">A/V 에지 서비스에서 NAT(Network Address Translation) IP 주소 및 구성을 사용하도록 설정하려면 **A/V** 에지 서비스가 NAT 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a3-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="cd5a3-109">사용하도록 설정된 에지 서비스의 경우 포트 아래에 **풀 FQDN** 및 **포트를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd5a3-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="cd5a3-110">액세스 **에지 서비스** 풀 FQDN 및 서비스를 고유하게 식별하는 포트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a3-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="cd5a3-111">웹  회의 에지 서비스 풀 FQDN(웹 회의 및 A/V에 대해 별도의 FQDN 및 IP 주소를 선택하지 않은 경우) 및 서비스를 고유하게 식별하는 포트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a3-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="cd5a3-112">**A/V** 에지 서비스 풀 FQDN(웹 회의에 대해 별도의 FQDN 및 IP 주소를 사용하도록 설정하고 A/V를 선택하지 않은 경우) 및 서비스를 고유하게 식별하는 포트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a3-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="cd5a3-113">**확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a3-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="cd5a3-114">**취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a3-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="cd5a3-115">**도움말**: 이 도움말 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5a3-115">**Help** Displays this help screen.</span></span>
  

