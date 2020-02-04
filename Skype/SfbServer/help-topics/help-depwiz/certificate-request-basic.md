---
title: 인증서 요청(기본)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: 이름 및 보안 설정 페이지에서는 친근 한 이름, 개인 및 공개 키 쌍의 비트 길이에 대 한 드롭다운 목록, 인증서의 개인 키를 내보낼 수 있는 것으로 표시 하는 확인란을 정의 하는 텍스트 상자를 제공 합니다.
ms.openlocfilehash: e3ee374ad9a1fc29f67b7f756dcb2fd0384bcabc
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687791"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="83e39-103">인증서 요청(기본)</span><span class="sxs-lookup"><span data-stu-id="83e39-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="83e39-104">**이름 및 보안 설정** 페이지에서는 **친근 한 이름**, 개인 및 공개 키 쌍의 **비트 길이** 에 대 한 드롭다운 목록, **인증서의 개인 키를 내보낼 수 있는 것으로 표시**하는 확인란을 정의 하는 텍스트 상자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e39-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="83e39-105">인증서의 이름(단순한 이름)은 간편하게 인지할 수 있는 이름으로, 인증서를 보는 사용자가 보다 쉽게 이름을 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e39-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="83e39-106">개인 키와 공개 키 쌍의 비트 길이는 1024, 2048 또는 4096으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83e39-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="83e39-107">**인증서의 개인 키를 내보낼** 수 있도록 표시에 대 한 확인란을 선택 하면 인증서와 개인 키를 다른 컴퓨터 또는 서버에 내보내고 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83e39-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="83e39-108">이 옵션이 필요한 경우는 MRAS(미디어 중계 인증 서비스)에 대한 에지 서버 풀을 만들 때뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="83e39-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="83e39-109">인증서 및 키 쌍의 보안을 유지 관리 하려면 절대적으로 필요한 경우에만 인증서의 개인 키를 내보낼 수 있도록 표시 옵션을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e39-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

