[[0 - 1. What is authentication? What is authorization?]]
2. Fetching data: What is the activity flow for getting data, for example, using Axios or React Query? How does fetching data differ when using useEffect?
3. What are the differences between normal CSS and Tailwind CSS in terms of definition and usage?
4. How is pagination implemented using a URL, and why is it necessary to push parameters onto the URL?
5. What tools are used to manage forms? What are the differences between using React Hook Form and native forms?
6. How many way to storage token? And how many ways are there to manage global state? Please provide a comparison. 
7. The best way to improve web performance optimization (Cách tốt nhất để tối ưu hoá hiệu suất trang web)
	- Tối ưu hoá hình ảnh: vì hình ảnh chiếm dung lượng lớn trên trang web, việc này bao gồm nén hình ảnh để giảm dung lượng nhưng không làm giảm đi chất lượng hình ảnh sẵn có.
	- Tối ưu hoá font chữ: sử dụng font từ hệ thống thay vì từ các gói cài đặt bên ngoài.
	- Giảm thiểu các tệp CSS & Javascript: loại bỏ đi các ký tự, các đoạn comment không cần thiết trong src code, ngoài ra có thể gộp các tệp CSS và Js thành các bản nhỏ hơn giúp giảm thời gian tải trang.
	- Giảm thiểu tính toàn vẹn của CSS & JS: loại bỏ các chức năng không cần thiết, sử dụng các gói thư viện nhỏ hơn hoặc chỉ sử dụng những phần cần thiết để giảm dung lượng tệp & tốc độ tải trang.
8. Eventloop?
	Là một cơ chế cho phép xử lý các tác vụ bất đồng bộ trong JS, sử dụng vòng lặp vô tận để kiểm tra, quản lý các tác vụ. Mặc dù là single-thread (tại một thời điểm chỉ thực hiện một tác vụ duy nhất), nhưng JS có thể xử lý nhiều tác vụ cùng lúc.
	Đọc: https://200lab.io/blog/event-loop-la-gi
9. What is CORS and how do you handle it in web applications?
	CORS is a security feature that restricts web applications from making requests to a domain from different from the one which served the web page. To handle it, configure the server to include CORS headers like Access-Control-Allow-Origin in the response, specifying which domains are allowed to access the resources.
10. What strategies would you employ to optimize the performancee of a web application?
	Optimization strategies include minimizing and compressing assest (CSS. JavaScript, images), implementing lazy loading for images and components, using CDN for static aassest, optimizing CSS selectors, and leveraging browser caching.
11. What are the SEO challenges with SPAs and how can they be addressed?
	SPAs oftern struggle with SEO as content is dynamically loaded, making it hard for search engine crawlers to index. Solutions include server-side rendering (SSR), using the History API to update URLs for the different views, and leveraging pre-rendering services or static site generators.