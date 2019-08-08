---
title: Skype 채팅방 시스템 비즈니스용 Skype 소프트웨어 라이선스
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 비즈니스용 Skype 소프트웨어 볼륨 라이선스가 있는지 확인 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: 731eefa49714fdced552c6cbedf4ecc288065d6b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235032"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="1f789-103">Skype 대화방 시스템: 비즈니스용 Skype 소프트웨어 라이선스</span><span class="sxs-lookup"><span data-stu-id="1f789-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="1f789-104">비즈니스용 Skype 소프트웨어 볼륨 라이선스가 있는지 확인 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1f789-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="1f789-105">Skype 채팅방 시스템은 설치 된 비즈니스용 Skype 클라이언트를 사용 하며,이는 소프트웨어 볼륨 라이센스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f789-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="1f789-106">첫 번째 Skype 대화방 시스템을 배포 하기 전에 KMS (키 관리 서버) 또는 MAK (복수 정품 인증 키)를 사용 하 여 배포의 볼륨 라이선스 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f789-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="1f789-107">KMS (키 관리 서버)</span><span class="sxs-lookup"><span data-stu-id="1f789-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="1f789-108">KMS가 있고 비즈니스용 Skype 볼륨 라이선스 정품 인증을 배포 하는 경우 Skype 대화방 시스템은 비즈니스용 Skype 클라이언트를 자동으로 정품 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f789-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="1f789-109">KMS의 현재 위치를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f789-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="1f789-110">명령 프롬프트에서 다음을 실행 합니다.`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="1f789-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="1f789-111">자세한 내용은 [DNS를 통해 Office 및 WINDOWS KMS 호스트를 찾고 승인 되지 않은 인스턴스를 제거 하는 방법을](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1f789-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="1f789-112">KMS를 설정 하려면 Office 2013 및 GVLKs의 [kms 정품 인증](https://technet.microsoft.com/library/ee624357.aspx) [및 Office 2013의 Active Directory 정품 인증](https://technet.microsoft.com/library/dn385360.aspx) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1f789-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="1f789-113">Lync에 대 한 Office 2013 일반 볼륨 라이선스 키: 2MG3G BNTT-3MFW9-KDQW3-TCK7R (이 키로 인해 Skype 대화방 시스템에서 네트워크에서 KMS를 찾을 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="1f789-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="1f789-114">볼륨 라이선스 서비스 센터 (VLSC)의 MAK (복수 정품 인증 키)</span><span class="sxs-lookup"><span data-stu-id="1f789-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="1f789-115">고객이 다른 볼륨 라이선스 소프트웨어를 사용 하는 경우 IT 부서는 VLSC를 사용 하 여 소프트웨어 정품 인증 및 볼륨 라이선스 계약 (VLA)을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f789-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="1f789-116">이렇게 하면 회사가 비즈니스용 Skype VL 정품 인증을 구매할 수 있으며 그 후에는 회사에서 Skype 채팅방 시스템 관리 콘솔의 입력에 대 한 MAK를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f789-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="1f789-117">VLA가 있는 고객은 계약을 관리 하 고 MAK를 구하는 데 사용 되는 VLSC 자격 증명을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f789-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="1f789-118">모르는 경우 고객의 재무 부서가 고객이 VLA에 대해 지불 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f789-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="1f789-119">MAK를 얻으려면 볼륨 라이선싱 서비스 센터에 액세스 하 여 규약을 보고 제품 키 (MAK)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f789-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="1f789-120">자세한 내용은 [볼륨 라이선싱 서비스 센터로](https://www.microsoft.com/Licensing/servicecenter/default.aspx)이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="1f789-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="1f789-121">VLSC 액세스 권한이 없는 Office 365의 MAK</span><span class="sxs-lookup"><span data-stu-id="1f789-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="1f789-122">고객이 볼륨 라이선스 계약서를 보유 하 고 있지 않은 경우 비즈니스용 Skype 정품 인증을 관리 하기가 훨씬 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="1f789-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="1f789-123">그러나 VLSC 없는 Office 365 고객은 Skype 대화방 시스템을 판매 하는 OEM에 다음 정보를 제공 하 여 판촉 MAK를 구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f789-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="1f789-124">회사 이름</span><span class="sxs-lookup"><span data-stu-id="1f789-124">Company name</span></span>
    
- <span data-ttu-id="1f789-125">배포 연락처 이름, 전자 메일 및 전화 번호</span><span class="sxs-lookup"><span data-stu-id="1f789-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="1f789-126">배포 된 시스템 수</span><span class="sxs-lookup"><span data-stu-id="1f789-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="1f789-127">배포 날짜</span><span class="sxs-lookup"><span data-stu-id="1f789-127">Deployment date</span></span>
    
- <span data-ttu-id="1f789-128">고객에 게 Microsoft 기술 계정 관리자가 있는 경우 TAM의 이름 및 연락처 정보</span><span class="sxs-lookup"><span data-stu-id="1f789-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

