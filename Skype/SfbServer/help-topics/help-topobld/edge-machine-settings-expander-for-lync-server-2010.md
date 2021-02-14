---
title: Lync Server 2010에 대한 에지 컴퓨터 설정 확장기
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
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 에지 서버 컴퓨터의 속성을 단일 에지 서버 또는 에지 풀의 구성원 컴퓨터로 편집하려면 서버 이름 및 IP 주소 구성 설정을 구성합니다.
ms.openlocfilehash: e25f68ec510cf15cd58872a8c584dc71aa939f48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807138"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b9fbc-103">Lync Server 2010에 대한 에지 컴퓨터 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="b9fbc-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b9fbc-104">에지 서버 컴퓨터의 속성을 단일 에지 서버 또는 에지 풀의 구성원 컴퓨터로 편집하려면 서버 이름 및 IP 주소 구성 설정을 **구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9fbc-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="b9fbc-105">**내부 이름 또는 FQDN**: DNS(Domain Name System)에서 참조되는 컴퓨터의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="b9fbc-106">**내부 IPv4 주소**: 이 컴퓨터에 대한 내부 NIC(네트워크 인터페이스 카드)의 IPv4 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="b9fbc-107">이 컴퓨터와 연결된 액세스 에지 **서비스** **외부 IPv4** 주소를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b9fbc-108">에지 서버 구성에 단일 IP 주소를 사용하기로 선택한 경우 액세스 에지 서비스의 외부 IPv4 주소만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="b9fbc-109">다른 에지 서비스는 액세스 에지 서비스와 동일한 IPv4 주소를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="b9fbc-110">편집할 수 있는 경우  이 컴퓨터와 연결된 웹 회의 서비스 **외부 IPv4** 주소를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="b9fbc-111">편집 가능한 경우 이 컴퓨터와 연결된 **A/V** 에지 서비스 **외부 IPv4** 주소를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="b9fbc-112">편집 가능한 경우 이 컴퓨터와 연결된 **NAT 사용 공용 IPv4 주소** 를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b9fbc-113">NAT 사용 공용 **IPv4** 주소의 구성 속성은 A/V 에지 서비스에 대해 NAT(Network Address Translation)를 제공해야 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="b9fbc-114">**확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="b9fbc-115">**취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="b9fbc-116">**도움말**: 이 도움말 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fbc-116">**Help** Displays this help screen.</span></span>
  

