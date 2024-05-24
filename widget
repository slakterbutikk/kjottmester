(function() {
    function loadReviews() {
        var placeId = 'ChIJF3QsBbk5OkYRZNWmEMSmgks';
        var apiKey = 'AIzaSyCytE3v_1Dkyl8CrnQB0JvIfQsUTFuqqhA';
        
        fetch(`https://maps.googleapis.com/maps/api/place/details/json?place_id=${placeId}&key=${apiKey}`)
            .then(response => response.json())
            .then(data => {
                var reviews = data.result.reviews;
                var container = document.querySelector('.google-reviews-widget');
                var reviewsHtml = reviews.map(review => `
                    <div class="review">
                        <h3>${review.author_name}</h3>
                        <p>${review.text}</p>
                        <small>Rating: ${review.rating}</small>
                    </div>
                `).join('');
                
                container.innerHTML = reviewsHtml;
            })
            .catch(error => console.error('Error fetching reviews:', error));
    }

    document.addEventListener('DOMContentLoaded', loadReviews);
})();
