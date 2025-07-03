<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>How to Publish InsightFlow Website</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2E3A8C;
            --accent: #0E9F9F;
            --light: #F8F9FA;
            --dark: #333333;
            --gray: #6c757d;
            --light-gray: #e9ecef;
            --transition: all 0.3s ease;
            --shadow: 0 4px 12px rgba(0,0,0,0.08);
            --shadow-hover: 0 8px 24px rgba(0,0,0,0.12);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: var(--dark);
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            line-height: 1.6;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            padding: 40px 0;
            margin-bottom: 40px;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 42px;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 10px;
        }

        .logo span {
            color: var(--accent);
        }

        .subtitle {
            font-size: 20px;
            color: var(--gray);
            max-width: 800px;
            margin: 0 auto;
        }

        .card-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-hover);
        }

        .card-header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
            color: white;
            padding: 25px;
            display: flex;
            align-items: center;
        }

        .card-icon {
            font-size: 32px;
            margin-right: 15px;
            width: 60px;
            height: 60px;
            background: rgba(255,255,255,0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .card-title {
            font-size: 24px;
            font-weight: 600;
        }

        .card-content {
            padding: 30px;
        }

        .steps {
            counter-reset: step-counter;
            list-style: none;
        }

        .steps li {
            margin-bottom: 25px;
            padding-left: 50px;
            position: relative;
        }

        .steps li:before {
            counter-increment: step-counter;
            content: counter(step-counter);
            position: absolute;
            left: 0;
            top: 0;
            width: 36px;
            height: 36px;
            background: var(--accent);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }

        .code-block {
            background: var(--light-gray);
            border-left: 4px solid var(--accent);
            padding: 15px;
            margin: 15px 0;
            border-radius: 0 8px 8px 0;
            font-family: monospace;
            overflow-x: auto;
        }

        .comparison-table {
            width: 100%;
            border-collapse: collapse;
            margin: 30px 0;
        }

        .comparison-table th, .comparison-table td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid var(--light-gray);
        }

        .comparison-table th {
            background: var(--primary);
            color: white;
        }

        .comparison-table tr:nth-child(even) {
            background: rgba(46,58,140,0.05);
        }

        .feature-badge {
            display: inline-block;
            padding: 5px 12px;
            background: var(--accent);
            color: white;
            border-radius: 20px;
            font-size: 12px;
            margin-right: 5px;
            margin-bottom: 5px;
        }

        .faq-section {
            margin: 50px 0;
        }

        .faq-item {
            margin-bottom: 20px;
            border: 1px solid var(--light-gray);
            border-radius: 8px;
            overflow: hidden;
        }

        .faq-question {
            background: white;
            padding: 20px;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .faq-answer {
            padding: 0 20px;
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease;
            background: white;
        }

        .faq-answer.active {
            padding: 20px;
            max-height: 500px;
        }

        footer {
            text-align: center;
            padding: 40px 0;
            margin-top: 40px;
            color: var(--gray);
            border-top: 1px solid var(--light-gray);
        }

        @media (max-width: 768px) {
            .card-container {
                grid-template-columns: 1fr;
            }
            
            .steps li {
                padding-left: 40px;
            }
            
            .steps li:before {
                width: 30px;
                height: 30px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">Publish <span>InsightFlow</span></div>
            <p class="subtitle">A step-by-step guide to deploying your article publishing platform to the web</p>
        </header>

        <div class="card-container">
            <!-- Free Hosting Options -->
            <div class="card">
                <div class="card-header">
                    <div class="card-icon">
                        <i class="fas fa-cloud-upload-alt"></i>
                    </div>
                    <div class="card-title">Free Hosting Options</div>
                </div>
                <div class="card-content">
                    <ol class="steps">
                        <li>
                            <strong>GitHub Pages</strong>
                            <p>Ideal for static sites with simple deployment</p>
                            <div class="code-block">
                                # Steps:<br>
                                1. Create GitHub repository<br>
                                2. Upload HTML/CSS/JS files<br>
                                3. Go to Settings > Pages<br>
                                4. Select branch (main) and folder (root)<br>
                                5. Your site: https://username.github.io/repo
                            </div>
                        </li>
                        <li>
                            <strong>Netlify</strong>
                            <p>Drag-and-drop deployment with continuous integration</p>
                            <div class="code-block">
                                # Steps:<br>
                                1. Go to app.netlify.com<br>
                                2. Drag/drop project folder<br>
                                3. Get instant URL<br>
                                OR<br>
                                1. Connect GitHub/GitLab repository<br>
                                2. Automatic deployment on push
                            </div>
                        </li>
                        <li>
                            <strong>Vercel</strong>
                            <p>Optimized for frontend frameworks with zero-config setup</p>
                            <div class="code-block">
                                # Steps:<br>
                                1. Install Vercel CLI: npm i -g vercel<br>
                                2. Run: vercel<br>
                                3. Follow prompts<br>
                                4. Deploy: vercel --prod
                            </div>
                        </li>
                    </ol>
                </div>
            </div>

            <!-- Paid Hosting Options -->
            <div class="card">
                <div class="card-header">
                    <div class="card-icon">
                        <i class="fas fa-server"></i>
                    </div>
                    <div class="card-title">Paid Hosting Options</div>
                </div>
                <div class="card-content">
                    <ol class="steps">
                        <li>
                            <strong>Shared Hosting</strong>
                            <p>(Bluehost, HostGator, SiteGround)</p>
                            <div class="code-block">
                                # Steps:<br>
                                1. Purchase hosting plan<br>
                                2. Access cPanel dashboard<br>
                                3. Upload files via File Manager<br>
                                4. Visit your domain
                            </div>
                        </li>
                        <li>
                            <strong>Cloud Hosting</strong>
                            <p>(AWS, Google Cloud, Azure)</p>
                            <div class="code-block">
                                # AWS S3 Example:<br>
                                1. Create S3 bucket<br>
                                2. Enable "Static website hosting"<br>
                                3. Upload files<br>
                                4. Set bucket policy for public access<br>
                                5. Access via bucket endpoint
                            </div>
                        </li>
                        <li>
                            <strong>VPS Hosting</strong>
                            <p>(DigitalOcean, Linode, Vultr)</p>
                            <div class="code-block">
                                # Basic Setup:<br>
                                1. Create droplet/instance<br>
                                2. SSH into server<br>
                                3. Install web server (Apache/Nginx)<br>
                                4. Configure virtual host<br>
                                5. Upload files to /var/www/html
                            </div>
                        </li>
                    </ol>
                </div>
            </div>

            <!-- Custom Domain Setup -->
            <div class="card">
                <div class="card-header">
                    <div class="card-icon">
                        <i class="fas fa-globe"></i>
                    </div>
                    <div class="card-title">Custom Domain Setup</div>
                </div>
                <div class="card-content">
                    <ol class="steps">
                        <li>
                            <strong>Purchase Domain</strong>
                            <p>From providers like Namecheap, GoDaddy, or Google Domains</p>
                        </li>
                        <li>
                            <strong>Configure DNS</strong>
                            <p>Point domain to your hosting provider:</p>
                            <div class="code-block">
                                # For Cloud Services:<br>
                                Create A record pointing to IP address<br>
                                OR<br>
                                Create CNAME record for subdomain
                            </div>
                        </li>
                        <li>
                            <strong>Hosting Configuration</strong>
                            <p>Set up domain in your hosting dashboard</p>
                            <div class="code-block">
                                # Netlify Example:<br>
                                1. Go to Domain settings<br>
                                2. Add custom domain<br>
                                3. Follow DNS instructions<br>
                                4. Enable HTTPS automatically
                            </div>
                        </li>
                    </ol>
                </div>
            </div>
        </div>

        <!-- Hosting Comparison Table -->
        <h2 style="margin: 40px 0 20px; color: var(--primary);">Hosting Service Comparison</h2>
        <table class="comparison-table">
            <thead>
                <tr>
                    <th>Service</th>
                    <th>Cost</th>
                    <th>Ease of Use</th>
                    <th>Best For</th>
                    <th>Features</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>GitHub Pages</td>
                    <td>Free</td>
                    <td>⭐️⭐️⭐️⭐️⭐️</td>
                    <td>Simple static sites</td>
                    <td>
                        <span class="feature-badge">HTTPS</span>
                        <span class="feature-badge">Custom Domain</span>
                        <span class="feature-badge">Version Control</span>
                    </td>
                </tr>
                <tr>
                    <td>Netlify</td>
                    <td>Free tier + paid</td>
                    <td>⭐️⭐️⭐️⭐️⭐️</td>
                    <td>Modern static sites</td>
                    <td>
                        <span class="feature-badge">CI/CD</span>
                        <span class="feature-badge">Forms</span>
                        <span class="feature-badge">Serverless</span>
                        <span class="feature-badge">HTTPS</span>
                    </td>
                </tr>
                <tr>
                    <td>Vercel</td>
                    <td>Free tier + paid</td>
                    <td>⭐️⭐️⭐️⭐️⭐️</td>
                    <td>React/Vue/Next.js apps</td>
                    <td>
                        <span class="feature-badge">Edge Network</span>
                        <span class="feature-badge">Serverless</span>
                        <span class="feature-badge">Preview Deploys</span>
                    </td>
                </tr>
                <tr>
                    <td>AWS S3</td>
                    <td>~$0.50/month</td>
                    <td>⭐️⭐️⭐️</td>
                    <td>Scalable static sites</td>
                    <td>
                        <span class="feature-badge">High Availability</span>
                        <span class="feature-badge">Low Cost</span>
                        <span class="feature-badge">Cloud Integration</span>
                    </td>
                </tr>
                <tr>
                    <td>Shared Hosting</td>
                    <td>$3-$10/month</td>
                    <td>⭐️⭐️⭐️⭐️</td>
                    <td>Traditional websites</td>
                    <td>
                        <span class="feature-badge">cPanel</span>
                        <span class="feature-badge">Email</span>
                        <span class="feature-badge">Database Support</span>
                    </td>
                </tr>
            </tbody>
        </table>

        <!-- Next Steps -->
        <h2 style="margin: 50px 0 20px; color: var(--primary);">Next Steps After Deployment</h2>
        <div class="card" style="margin-bottom: 40px;">
            <div class="card-header">
                <div class="card-icon">
                    <i class="fas fa-rocket"></i>
                </div>
                <div class="card-title">Optimization & Launch</div>
            </div>
            <div class="card-content">
                <ol class="steps">
                    <li>
                        <strong>Enable HTTPS</strong>
                        <p>All hosting providers offer free SSL certificates</p>
                        <div class="code-block">
                            # Netlify/AWS/Vercel: Automatic HTTPS<br>
                            # Shared Hosting: Use cPanel SSL/TLS manager<br>
                            # Cloudflare: Free universal SSL
                        </div>
                    </li>
                    <li>
                        <strong>Performance Optimization</strong>
                        <p>Ensure fast loading times</p>
                        <div class="code-block">
                            - Compress images (tinypng.com)<br>
                            - Minify CSS/JS (cssminifier.org)<br>
                            - Enable Gzip compression<br>
                            - Implement caching headers
                        </div>
                    </li>
                    <li>
                        <strong>Submit to Search Engines</strong>
                        <p>Google Search Console & Bing Webmaster Tools</p>
                        <div class="code-block">
                            # Steps for Google:<br>
                            1. Verify ownership (HTML file or DNS record)<br>
                            2. Submit sitemap.xml<br>
                            3. Monitor search performance
                        </div>
                    </li>
                    <li>
                        <strong>Set Up Analytics</strong>
                        <p>Track visitor behavior and traffic sources</p>
                        <div class="code-block">
                            // Google Analytics snippet<br>
                            &lt;script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"&gt;&lt;/script&gt;<br>
                            &lt;script&gt;<br>
                            &nbsp;&nbsp;window.dataLayer = window.dataLayer || [];<br>
                            &nbsp;&nbsp;function gtag(){dataLayer.push(arguments);}<br>
                            &nbsp;&nbsp;gtag('js', new Date());<br>
                            &nbsp;&nbsp;gtag('config', 'GA_MEASUREMENT_ID');<br>
                            &lt;/script&gt;
                        </div>
                    </li>
                </ol>
            </div>
        </div>

        <!-- FAQ Section -->
        <div class="faq-section">
            <h2 style="margin-bottom: 30px; color: var(--primary);">Frequently Asked Questions</h2>
            
            <div class="faq-item">
                <div class="faq-question" onclick="toggleFAQ(this)">
                    Which hosting option is best for beginners?
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="faq-answer">
                    <p>For absolute beginners, Netlify is the best choice because:</p>
                    <ul>
                        <li>Drag-and-drop deployment requires no technical knowledge</li>
                        <li>Free tier includes custom domain and HTTPS</li>
                        <li>Automatic builds from Git repositories</li>
                        <li>No server configuration needed</li>
                    </ul>
                </div>
            </div>
            
            <div class="faq-item">
                <div class="faq-question" onclick="toggleFAQ(this)">
                    How do I point my domain to GitHub Pages?
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="faq-answer">
                    <p>Follow these steps:</p>
                    <ol>
                        <li>Create a file named CNAME in your repository (no extension)</li>
                        <li>Add your domain name in this file (e.g., "yourdomain.com")</li>
                        <li>In your domain registrar's DNS settings:
                            <ul>
                                <li>Create A records pointing to GitHub's IP addresses:
                                    <div class="code-block">
                                        185.199.108.153<br>
                                        185.199.109.153<br>
                                        185.199.110.153<br>
                                        185.199.111.153
                                    </div>
                                </li>
                                <li>OR create a CNAME record pointing to yourusername.github.io</li>
                            </ul>
                        </li>
                        <li>Wait up to 24 hours for DNS propagation</li>
                    </ol>
                </div>
            </div>
            
            <div class="faq-item">
                <div class="faq-question" onclick="toggleFAQ(this)">
                    Should I choose free or paid hosting?
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="faq-answer">
                    <p>It depends on your needs:</p>
                    <table class="comparison-table">
                        <tr>
                            <th>Free Hosting</th>
                            <th>Paid Hosting</th>
                        </tr>
                        <tr>
                            <td>Good for testing and small projects</td>
                            <td>Necessary for production business sites</td>
                        </tr>
                        <tr>
                            <td>Limited resources and bandwidth</td>
                            <td>Higher performance and resources</td>
                        </tr>
                        <tr>
                            <td>May have provider branding</td>
                            <td>Complete professional appearance</td>
                        </tr>
                        <tr>
                            <td>Limited customer support</td>
                            <td>Priority customer support</td>
                        </tr>
                        <tr>
                            <td>Best for: Personal projects, portfolios, demos</td>
                            <td>Best for: Business sites, e-commerce, high-traffic sites</td>
                        </tr>
                    </table>
                </div>
            </div>
        </div>

        <footer>
            <p>© 2023 InsightFlow Publishing Platform | Created with ❤️ for content creators</p>
            <p>Need help? Contact: support@insightflow.com</p>
        </footer>
    </div>

    <script>
        function toggleFAQ(element) {
            const answer = element.nextElementSibling;
            const icon = element.querySelector('i');
            
            answer.classList.toggle('active');
            
            if (answer.classList.contains('active')) {
                icon.classList.remove('fa-chevron-down');
                icon.classList.add('fa-chevron-up');
            } else {
                icon.classList.remove('fa-chevron-up');
                icon.classList.add('fa-chevron-down');
            }
        }
    </script>
</body>
</html>
